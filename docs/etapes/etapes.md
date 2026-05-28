# Etape 3: PROGRAMMATION & VISION

### 1 Les tags Aruco — Principe et rôle dans le projet

Les tags Aruco sont des marqueurs visuels carrés composés d'une **bordure noire distincte** et d'une **matrice interne de pixels binaires** (noirs ou blancs), formant un code unique identifiable par un algorithme de détection. Leur conception a été pensée pour être robuste aux variations d'éclairage, de distance et d'angle de vue, ce qui en fait un choix particulièrement adapté aux applications de vision par ordinateur en temps réel.

Dans le cadre de notre projet Puzzle Bot, les tags Aruco sont utilisés pour **localiser les pièces du puzzle** dans le champ de la caméra. Chaque tag est associé à un identifiant numérique unique, ce qui permet au système de distinguer les différentes pièces et de déterminer leur position dans l'espace de travail.

### 2 Matériel utilisé

La détection est assurée par une **caméra à port USB**, positionnée au-dessus du plateau de travail de manière à couvrir l'ensemble de la zone où sont déposées les pièces du puzzle. Elle est connectée directement à l'ordinateur qui exécute le script Python de traitement d'image.


### 3 Implémentation Python — Détection des tags Aruco

Le traitement d'image est réalisé en **Python**, en s'appuyant sur les bibliothèques **OpenCV** et son module **aruco**. Le script capture le flux vidéo en temps réel depuis la caméra USB, analyse chaque image et y détecte les tags Aruco présents.

Le fonctionnement du code suit les étapes suivantes :

**Capture du flux vidéo**: La caméra est initialisée via OpenCV, qui capture les images frame par frame en continu.

**Détection des marqueurs**: Chaque image est analysée par la fonction de détection Aruco, qui recherche les contours carrés caractéristiques des marqueurs et décode leur matrice binaire interne pour en extraire l'identifiant.

**Affichage des résultats** — Lorsqu'un tag est détecté, plusieurs éléments visuels sont superposés à l'image en temps réel :
- Le **contour du tag est entouré en vert**, confirmant visuellement la détection.
- L'**identifiant numérique du tag** est affiché à proximité du marqueur.
- Un **carré rouge est placé sur le coin supérieur gauche** du tag, indiquant le point de référence de position retenu pour ce marqueur.

**Extraction des coordonnées** — Les coordonnées pixel du tag détecté sont extraites et peuvent être transmises au reste du système pour calculer la position réelle de la pièce sur le plateau.


### 4 Perspectives d'amélioration

Bien que la détection des tags Aruco soit fonctionnelle pour localiser les pièces du puzzle, plusieurs axes d'amélioration sont envisagés pour les prochaines itérations :

**Calibration de la caméra** : L'intégration d'une étape de calibration permettrait de corriger les distorsions optiques de la caméra et d'améliorer la précision du calcul de position réelle à partir des coordonnées pixel.

**Détection du repère de travail**: Un tag Aruco de référence positionné à un endroit fixe du plateau permettrait d'établir automatiquement la correspondance entre le repère image et le repère physique de la machine, rendant le système plus robuste aux variations de positionnement de la caméra.

**Communication avec l'Arduino** : Une fois les coordonnées extraites, la prochaine étape consiste à les transmettre à l'Arduino via liaison série, afin que la machine puisse se déplacer automatiquement vers la pièce détectée et engager le processus de préhension.
