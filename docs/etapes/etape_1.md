### Etape 1: CONCEPTION MECANIQUE (Onshape) 

### Vue d'ensemble de la structure
La conception mécanique de notre Puzzle Bot a été intégralement réalisée sous **Onshape**, un logiciel de CAO collaboratif en ligne permettant à l'ensemble de l'équipe de travailler simultanément sur le même document. Notre machine repose sur une architecture cartésienne à trois axes **(X, Y, A)**. La structure repose sur deux longerons horizontaux en **profilés aluminium 20X20** disposés parallèlement, qui constituent le châssis principal de la machine et définissent la course de l'axe Y. Quatre **pieds support** viennent ancrer et surélever l'ensemble aux quatre coins, assurant la stabilité de la machine sur son plan de travail. Entre les deux longerons est tendu le **plateau de travail en bois**, qui constitue la surface sur laquelle les pièces du puzzle sont déposées et manipulées.

![image](images/groupe 6.png)  


### Architecture des axes

**Axe Y — déplacement longitudinal**
Le chariot principal se déplace le long des deux longerons en profilés 20X20 grâce à un système de courroie et de roulements. Deux **moteurs pas à pas** situés de part et d'autre de la structure entraînent le déplacement synchronisé du portique transversal le long de cet axe.

**Axe A — déplacement transversal**
Le portique transversal, coulisse perpendiculairement aux longerons. Il est entraîné par un troisième moteur pas à pas et porte le chariot de l'axe X. Sa conception intègre des renforts triangulaires imprimés en 3D de chaque côté, qui assurent la rigidité angulaire de l'ensemble.

**Axe X — déplacement vertical**
La tête de préhension est montée sur l'axe X, dont le mécanisme de translation verticale est logé dans le bloc central bleu en haut du portique. Un moteur pas à pas dédié pilote la descente et la remontée de la ventouse, permettant de saisir une pièce en surface et de la soulever pour la déplacer.

---

### Choix de conception et justifications

**Profilés aluminium 2020** : Le recours aux profilés aluminium à fente en V de section 20×20 mm a été privilégié pour leur rigidité, leur légèreté et leur modularité. Leur système de fixation par écrous à glissière permet d'ajuster et de repositionner les éléments mécaniques sans usinage supplémentaire, ce qui facilite les itérations lors des phases de prototypage.

**Pièces imprimées en 3D** — Les supports de roulements, les chariots, les renforts angulaires et les supports moteurs ont ét& entièrement réalisés par impression 3D. Ce choix nous a permis d'adapter précisément la géométrie de chaque pièce aux contraintes fonctionnelles du robot, tout en conservant une grande liberté de modification entre deux versions.

### Démarche de prototypage et d'itération

La conception n'a pas été figée dès la première version. Plusieurs éssaies ont été nécessaires pour affiner les dimensions, corriger les jeux mécaniques et améliorer l'assemblabilité des pièces. Chaque modification a été apportée directement dans le document Onshape. Les pièces critiques ont fait l'objet d'impressions de test avant la fabrication de la version finale, afin de valider les ajustements dimensionnels et les tolérances d'assemblage.
