# Détection des tags Aruco

Durant le projet, nous avons utilisé des tags Aruco. Les tags Aruco sont des carré noir et blanc, qui peuvent être détecter grâce à la bibliothèque OpenCV. Chaque tag possédant un identifiant différent, nous les avons utilisés pour permettre au robot de détecter les différentes pièces du puzzle. Pour cela, nous avons collé un tag sur chacune des pièces du puzzle. La caméra pouvait ainsi repérer les pièces grâce au tag Aruco.

Nous avons ensuite utilisé deux codes sur Python pour pouvoir détecter les différents tags. Nous avons donc importé la bibliothèque OpenCV dans les codes Pyhton pour détecter les tags grâce à la commande import cv2

## DroidCam
Pour effectuer les tests avant l'arrivée de la caméra, nous avons utilisé le logiciel DroidCam. Ce logiciel permet de transformer la caméra d’un téléphone portable en webcam. Cela a permis de tester les deux codes python sans utiliser la caméra réelle et la remplacer par le téléphone.
Pour cela, le logiciel et l’ordinateur ont été connectés ensemble grâce à l’adresse IP du téléphone portable. Pour relier la caméra du téléphone à l'ordinateur, le logiciel DroidCam a été installé aussi bien sur l'ordinateur que sur le téléphone portable. Sur le téléphone, l'adresse IP du téléphone portable (ainsi qu'un port pour DroidCam) sont inscrits. Sur l'ordinateur, nous pouvons réaliser la caméra du téléphone en renseignant l'adresse IP du téléphone connecté. Une fois cela effectué, tout ce que la caméra intégré au téléphone filme est directement envoyé à l'ordinateur. Ce qui a permis de tester les deux codes suivants. 

## 1er code : Détection des tags
Le premier code a permis de détecter les tags Aruco. Dès que la caméra détecte un tags Aruco, il entourera ce tags avec un contour vert. Un point rouge apparaîtra sur le côté haut à gauche pour préciser la position du tag et l’identifiant du tag apparaîtra.

import cv2
import time

\# --- Initialisation caméra ---
cap = cv2.VideoCapture(2)
time.sleep(1)

for _ in range(10):
    cap.read()

\# --- Initialisation ArUco (compatible OpenCV 4.13) ---
aruco_dict = cv2.aruco.getPredefinedDictionary(cv2.aruco.DICT_4X4_50)
aruco_params = cv2.aruco.DetectorParameters()

while True:
    ret, frame = cap.read()
    if not ret:
        print("Aucune image reçue...")
        break

    # --- Détection ArUco ---
    corners, ids, rejected = cv2.aruco.detectMarkers(
        frame,
        aruco_dict,
        parameters=aruco_params
    )

    # --- Dessiner les marqueurs détectés ---
    if ids is not None:
        cv2.aruco.drawDetectedMarkers(frame, corners, ids)

    # --- Affichage ---
    cv2.imshow("DroidCam + ArUco", frame)

    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()

Nous avons commencé par importer la bibliothèque cv2 pour détecter les tags Aruco.
Nous avons ensuite initialisé la caméra grâce à la commande cap = cv2.VideoCapture(2). Cette commande permet d'ouvrir la caméra numéro 2. A noter que selon si l'on utilise la caméra réelle ou DroidCam, le numéro peut changer (le 2 étant le numéro de la caméra réelle).
Nous avons ensuite initialisé le nombre de tags que la caméra pouvait détecter. Le code aruco_dict = cv2.aruco.getPredefinedDictionary(cv2.aruco.DICT_4X4_50) permet donc de créer un dictionnaire contenant les 50 premiers tags Aruco.Tous les tags dans ce dictionnaire peut donc être détecté, ce qui était largement suffisant pour un puzzle de 4 pièces.
Le programme détecte les tags. Dès qu'un tag appartenant au dictionnaire est repéré par la caméra, l'id de ce tag, ainsi le coin en haut à gauche de celui-ci seront repéré par la caméra.

## 2eme code :
Tout comme le premier code, il permet de détecter les tags en affichant un carré vert autour du tag, et un carré rouge apparaît sur le coin en haut à gauche de chaque tag pour détecter la position de celui-ci. Cependant, ce code permet en plus d’afficher le centre des tags détecté par un point rouge, ainsi que la position du centre de chaque tags en fonction de x et y (en pixel)

import cv2
import numpy as np
import math

\# --- Camera ---
cap = cv2.VideoCapture(2, cv2.CAP_DSHOW)

if not cap.isOpened():
    print("Impossible d'ouvrir la caméra")
    exit()

\# --- ArUco ---
aruco_dict = cv2.aruco.getPredefinedDictionary(
    cv2.aruco.DICT_4X4_50
)

aruco_params = cv2.aruco.DetectorParameters()

while True:

    ret, frame = cap.read()

    if not ret:
        print("Pas d'image")
        break

    corners, ids, rejected = cv2.aruco.detectMarkers(
        frame,
        aruco_dict,
        parameters=aruco_params
    )

    if ids is not None:

        cv2.aruco.drawDetectedMarkers(frame, corners, ids)

        for i in range(len(ids)):

            # Coins du tag
            pts = corners[i][0]

            # Centre
            cx = int(np.mean(pts[:, 0]))
            cy = int(np.mean(pts[:, 1]))

            # Coin 0 -> coin 1
            x1, y1 = pts[0]
            x2, y2 = pts[1]

            # Angle
            angle = math.degrees(
                math.atan2(y2 - y1, x2 - x1)
            )

            # ID
            tag_id = ids[i][0]

            # Affichage texte
            text = f"ID:{tag_id} A:{angle:.1f}"

            cv2.putText(
                frame,
                text,
                (cx, cy),
                cv2.FONT_HERSHEY_SIMPLEX,
                0.6,
                (0, 255, 0),
                2
            )

            # Centre
            cv2.circle(frame, (cx, cy), 5, (0, 0, 255), -1)

            print(
                f"ID={tag_id} X={cx} Y={cy} Angle={angle:.1f}"
            )

    cv2.imshow("Aruco Tracking", frame)

    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()

Tout comme le code précédent, nous avons importé la bibliothèque cv2, ainsi que créé un dictionnaire contenant les 50 premier tags pour les même raisons. Nous avons également importé les bibliothèques numpy et mat qui ont permis de réaliser les calculs de détection du centre des tags, ou de la position de ces derniers. Dès qu'un tag est détecté par la caméra, la position de ces quatres sont stockées dans la variable pts.
Cela permet de calculer le centre des tags grâce à la commande mean. La commande np.mean() calcule la moyenne des quatres coins d'un tag. En obtenant la moyenne des coordonnées x et y (noté cx et cy dans le programme), nous avons pu obtenir la détection du centre de chaque tag.
Nous avons également détecté l'orientation de chaque tags grâce à la fonction math.atan2, commande qui permet de calculer l'angle formé entre le tag et l'axe horizontal de la caméra (la fonction degrees permettant de convertir cet angle en degrés).
