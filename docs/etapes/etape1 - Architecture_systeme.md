### Etape 1 : architecture-systeme.md (Onshape) 

### Vue d'ensemble de la structure

![Vue d'ensemble](https://i.postimg.cc/FzKfBRTL/Capture-d-ecran-2026-06-15-a-14-19-41.png)

L'ensemble du Puzzle Bot est constitué de plusieurs pièces conçues sous Onshape et fabriquées principalement par impression 3D. Chaque composant possède une fonction spécifique permettant d'assurer la rigidité de la structure, le guidage des axes ou le maintien des différents actionneurs.

Cette vue représente l'intégralité du Puzzle Bot assemblé. On distingue :

- Le châssis principal en profilés aluminium 20×20 mm.
- Le plateau de travail perforé permettant la fixation des différents éléments.
- Le portique supportant l'axe transversal.
- Le système de préhension chargé de manipuler les pièces du puzzle.
- Les différents supports moteurs et renforts mécaniques.

L'objectif de cette architecture est de permettre le déplacement précis de la tête de préhension sur toute la surface.



---

### 1. Support moteur principal
![Support moteur principal](https://i.postimg.cc/g24BRtfn/Capture-d-ecran-2026-06-15-a-14-40-13.png)

Cette pièce sert à fixer les moteurs pas à pas sur la structure.

#### Fonctions
- Maintenir fermement le moteur.
- Assurer l'alignement avec les poulies et les courroies.
- Transmettre correctement les efforts mécaniques.

#### Choix de conception
- Forme triangulaire pour améliorer la rigidité.
- Perçages normalisés pour moteurs NEMA.
- Base large facilitant la fixation sur les profilés.

---


### 2. Chariot de préhension

![Chariot de préhension](https://i.postimg.cc/HkPRRP3c/Capture-d-ecran-2026-06-15-a-14-49-54.png)

Cette pièce constitue le cœur du système de manipulation.

#### Fonctions
- Supporter la ventouse.
- Guider le mouvement vertical.
- Recevoir les différents capteurs et actionneurs.

#### Particularités
- Forme compacte pour limiter le poids embarqué.
- Intégration des logements de fixation.
- Réduction de l'encombrement afin d'augmenter la précision.

---


### 3. Bras support de ventouse

![image](https://i.postimg.cc/wTRs1p6j/image.png) ![image](https://i.postimg.cc/DwbRZ5pr/Capture-d-ecran-2026-06-16-a-22-17-40.png)

Cette pièce relie la tête de préhension au système de guidage vertical.

#### Fonctions 
- Supporter la ventouse.
- Positionner la tête de préhension.
- Transmettre les mouvements verticaux.

#### Choix de conception
- Géométrie allongée limitant l'encombrement.
- Masse réduite pour améliorer la rapidité des déplacements.
- Fixations intégrées simplifiant l'assemblage.

- Forme cylindrique adaptée au montage de la ventouse.
- Fixation simple par vis.
- Faible masse afin de limiter l’inertie du système mobile.
- Fabrication par impression 3D facilitant les modifications.

---

#### Intérêt pour le projet

Cette conception permet de saisir précisément les pièces du puzzle sans perturber leur position. La légèreté de l'ensemble améliore également la rapidité et la précision des déplacements du robot.

---


### 4.Platine de fixation des roulements

![image](https://i.postimg.cc/hGLhRL9L/Capture-d-ecran-2026-06-16-a-23-39-49.png)

Cette pièce permet l'installation des roulements utilisés dans les systèmes de guidage et de rotation.

#### Fonctions
- Maintenir les roulements.
- Garantir le centrage des axes.
- Réduire les frottements.
- Améliorer la précision des déplacements.
  
#### Choix de conception
- Logement central adapté au roulement.
- Quatre points de fixation.
- Maintenance et remplacement facilités.

---


### 5. Support inférieur du portique

![image](https://i.postimg.cc/44qGwKcB/Capture-d-ecran-2026-06-16-a-23-42-16.png)

Cette pièce assure la liaison entre le montant vertical et le châssis du robot.

#### Fonctions
- Maintenir le montant vertical.
- Répartir les charges sur le châssis.
- Garantir la stabilité du portique.

#### Choix de conception
- Base élargie améliorant la stabilité.
- Renforts intégrés limitant les déformations.
- Fixation robuste sur les profilés aluminium.

---


## 6. Support de maintien de courroie

Cette pièce permet de maintenir et de fixer la courroie de transmission utilisée pour le déplacement des axes du Puzzle Bot. Elle assure une liaison fiable entre la courroie et les éléments mobiles du système.

![image](https://i.postimg.cc/CLcQJXX9/Capture-d-ecran-2026-06-16-a-23-51-00.png)

#### Fonctions
- Maintenir la courroie en position.
- Assurer la transmission des efforts de déplacement.
- Empêcher le glissement de la courroie.
- Garantir la précision des mouvements des axes.

#### Choix de conception
- Forme adaptée au serrage de la courroie.
- Géométrie compacte limitant l'encombrement.
- Fixation simple facilitant le montage et le démontage.
- Fabrication par impression 3D permettant des modifications rapides.

---

### Intérêt pour le projet

Cette pièce joue un rôle essentiel dans la transmission du mouvement. Un maintien correct de la courroie permet d'obtenir des déplacements précis et répétables, indispensables pour le positionnement de la tête de préhension.

---


## 7. Système de support de caméra

Le système de vision constitue un élément essentiel du Puzzle Bot. Il permet d'obtenir une vue globale de la zone de travail afin de détecter les pièces du puzzle ainsi que les marqueurs ArUco utilisés pour leur identification et leur localisation.

Afin de positionner la caméra à une hauteur suffisante au-dessus du plateau, un mât vertical en profilé aluminium de 40 cm a été intégré à la structure. Plusieurs pièces imprimées en 3D ont été spécialement conçues pour assurer le maintien, le guidage et la fixation de cet ensemble.

L'objectif principal de ce système est de garantir une position stable et précise de la caméra tout en limitant les vibrations susceptibles d'altérer la qualité des images acquises.

### 7.1 Support inférieur du mât de caméra

![image](https://i.postimg.cc/qvk3wBWB/Capture-d-ecran-2026-06-16-a-23-59-54.png)

Cette pièce constitue la base du système de vision. Elle assure la liaison entre le châssis principal du robot et le profilé aluminium vertical supportant la caméra.

#### Fonctions
- Maintenir le profilé aluminium vertical.
- Supporter le poids du système de vision.
- Répartir les efforts mécaniques sur le châssis.
- Garantir la stabilité du mât.

#### Choix de conception
- Logement carré adapté au profilé aluminium 20×20 mm.
- Base large augmentant la rigidité.
- Renforts intégrés limitant les déformations.
- Fixation robuste sur la structure principale.



### 7.2 Support supérieur du mât

![image](https://i.postimg.cc/RFfh92jS/Capture-d-ecran-2026-06-17-a-00-00-55.png)

Cette pièce est positionnée à l'extrémité supérieure du portique. Elle permet de fixer et de guider le profilé aluminium supportant la caméra.

#### Fonctions
- Maintenir l'alignement du profilé vertical.
- Renforcer la rigidité du système de vision.
- Réduire les vibrations du mât.
- Garantir la perpendicularité de l'ensemble.

#### Choix de conception
- Forme enveloppante assurant un bon maintien.
- Multiples points de fixation.
- Géométrie optimisée pour l'impression 3D.
- Montage simple et rapide.



### 7.3 Support de fixation de la caméra

![image](https://i.postimg.cc/T10R3xQ1/Capture-d-ecran-2026-06-17-a-00-02-11.png)

Cette pièce est située à l'extrémité du mât et reçoit directement la caméra. Elle permet de positionner le capteur de manière stable au-dessus du plateau de travail.

#### Fonctions
- Supporter la caméra.
- Garantir son orientation correcte.
- Assurer une fixation rigide.
- Faciliter le réglage et le remplacement du système de vision.

#### Choix de conception
- Interface adaptée à la caméra utilisée.
- Faible masse afin de limiter les contraintes sur le mât.
- Multiples points de fixation.
- Fabrication par impression 3D permettant des modifications rapides.

---

### Intérêt pour le projet

Le système de support de caméra joue un rôle fondamental dans le fonctionnement du Puzzle Bot. En positionnant la caméra à environ 40 cm au-dessus du plateau, il permet d'obtenir une vue complète de la zone de travail. Les images acquises sont ensuite exploitées par les algorithmes de vision artificielle pour détecter les pièces du puzzle et les marqueurs ArUco. La stabilité de ce système est essentielle pour garantir la précision des mesures et la fiabilité de l'assemblage automatique du puzzle.

---


### 8.Support de maintien du profilé du bloc central

![image](https://i.postimg.cc/NGRh7Q6Q/Capture-d-ecran-2026-06-17-a-00-20-05.png)

Cette pièce assure la fixation et le maintien du profilé aluminium reliant le bloc central aux autres éléments de la structure. Elle garantit la rigidité de l'ensemble et contribue à la stabilité du système de préhension.

#### Fonctions

- Maintenir le profilé aluminium du bloc central.
- Garantir l'alignement de la structure.
- Répartir les efforts mécaniques transmis par les déplacements.
- Renforcer la rigidité de l'ensemble mobile.

#### Choix de conception

- Logement carré adapté au profilé aluminium 20×20 mm.
- Platine de fixation comportant plusieurs points d'ancrage.
- Géométrie renforcée limitant les déformations.
- Fabrication par impression 3D permettant une intégration précise dans l'assemblage.

---

#### Intérêt pour le projet

Cette pièce participe à la stabilité mécanique du bloc central. Elle permet de maintenir correctement le profilé aluminium tout en limitant les vibrations et les déformations susceptibles d'affecter la précision des déplacements du Puzzle Bot.

---

