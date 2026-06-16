### Etape 1 : architecture_systeme.md (Onshape) 

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


### 3. Ensemble support de préhension

Cet ensemble est constitué d'un bras de liaison vertical et d'un support cylindrique permettant le montage de la ventouse. Il constitue la partie terminale du système de préhension du Puzzle Bot.

L'ensemble assure le positionnement précis de la ventouse au-dessus des pièces du puzzle et transmet les mouvements verticaux commandés par le moteur de l'axe Z.

#### Fonctions

- Supporter la ventouse.
- Assurer la liaison entre le mécanisme de translation verticale et la tête de préhension.
- Garantir le bon alignement de la ventouse.
- Transmettre les efforts lors de la prise et du déplacement des pièces.
- Maintenir la stabilité de la tête de préhension pendant les déplacements.

#### Choix de conception

- Bras vertical allongé permettant de déporter la ventouse sous le mécanisme.
- Support cylindrique facilitant l'insertion et le maintien de la ventouse.
- Conception légère afin de réduire l'inertie des pièces mobiles.
- Fabrication par impression 3D permettant des modifications rapides lors du prototypage.

  ![image](https://i.postimg.cc/wTRs1p6j/image.png) ![image](https://i.postimg.cc/DwbRZ5pr/Capture-d-ecran-2026-06-16-a-22-17-40.png)

#### Intérêt pour le projet

Cette conception permet de saisir précisément les pièces du puzzle sans perturber leur position. La légèreté de l'ensemble améliore également la rapidité et la précision des déplacements du robot.
### 4. Support de guidage supérieur

Cette pièce accueille un élément de guidage cylindrique.

#### Fonctions

- Maintenir les axes de guidage.
- Garantir l'alignement mécanique.
- Réduire les jeux lors des déplacements.

---

### 5. Platine de fixation des roulements

Cette platine est utilisée pour fixer les roulements participant au guidage des axes.

#### Fonctions

- Maintenir les roulements.
- Répartir les charges mécaniques.
- Faciliter les opérations de maintenance.

