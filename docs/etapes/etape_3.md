# Détection des tags Aruco

Durant le projet, nous avons utiliser deux codes sur Python pour pouvoir détecter les différents tags. Nous avons également utilisé le logiciel OpenCV pour détecter les tags en important la bibliothèques sur Pyhton (import cv2)

## DroidCam
Pour effectuer les test, nous avons utiliser le logiciel DroidCam. Ce logiciel permet de transformer la caméra d’un téléphone portable en webcam. Cela a permis de tester les deux codes suivant sans utiliser la caméra réelle et la remplacer par le téléphone.
Pour cela, le logiciel et l’ordinateur ont été connecté ensemble grâce à l’adresse IP du téléphone portable.

## 1er code : Détection des tags
Ce code permet de détecter les tags Aruco. Dès que la caméra détecte un tags Aruco, il entourera ce tags avec un contour vert., un point rouge apparaîtra sur le coté haut à gauche pour préciser la position du tag et l’identifiant du tag apparaîtra.

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


## 2eme code :
Ce code permet de détecter les tags Aruco, tout en affichant la dictance entre la caméra et le tag détecter. Tout comme le premier code, il permet de détecter les tags en affichant un carré vert autour du tag, et un carré rouge est apparaît sur le coin en haut à gauche de chaque tag pour détecter la position de celui ci. Cependant, ce code permet de plus d’afficher le centre des tags détecté par un point rouge, ainsi que la position du centre de chaque tags en fonction de x et y (en pixel)

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
