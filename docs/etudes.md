
# Études et choix techniques des composants utilisés

# 1. Carte Arduino Uno
L'Arduino Uno constitue l'unité centrale de commande du Puzzle Bot. Basée sur le microcontrôleur ATmega328P, cette carte assure l'exécution du programme embarqué et la coordination de l'ensemble des composants électroniques du système. Elle reçoit les instructions issues du programme de contrôle, génère les signaux nécessaires au pilotage des actionneurs et traite les informations provenant des différents capteurs.

Le choix de l'Arduino Uno s'est imposé grâce à sa simplicité de programmation, sa grande communauté d'utilisateurs et sa compatibilité directe avec le CNC Shield V3 utilisé dans notre projet. Son faible coût et sa fiabilité en font également une solution particulièrement adaptée au prototypage robotique.


<img width="725" height="543" alt="Capture d&#39;écran 2026-06-01 175616" src="https://github.com/user-attachments/assets/437a57c6-d2e1-49d0-bcba-baf3ff57f3b5" />

# 2. CNC Shield V3

Le CNC Shield V3 est une carte d'extension spécialement conçue pour faciliter le pilotage de moteurs pas à pas à partir d'un Arduino Uno. Fixé directement sur la carte Arduino, il permet d'accueillir plusieurs drivers moteurs et simplifie considérablement le câblage du système.

Dans le Puzzle Bot, le CNC Shield assure l'interface entre l'Arduino et les différents moteurs pas à pas responsables des déplacements de la machine. Il distribue les signaux de commande STEP et DIR générés par l'Arduino vers les drivers A4988 et fournit également les connecteurs nécessaires au branchement des capteurs de fin de course.

Ce composant a été retenu pour sa compatibilité avec les systèmes de commande numériques, sa facilité d'intégration et sa large utilisation dans les projets de machines CNC et d'impression 3D.

<img width="767" height="528" alt="Capture d&#39;écran 2026-06-01 175659" src="https://github.com/user-attachments/assets/0fb276dd-7210-406e-91ab-d77d07ea0e0b" />

# 3. Drivers A4988

Les drivers A4988 sont des modules électroniques destinés au pilotage des moteurs pas à pas. Ils jouent un rôle essentiel en servant d'interface de puissance entre l'Arduino et les moteurs.

L'Arduino ne pouvant fournir que de faibles courants électriques, les drivers reçoivent les signaux logiques STEP et DIR puis génèrent les courants nécessaires à l'alimentation des bobines des moteurs. Ils permettent également la gestion du micro-pas, améliorant ainsi la précision et la fluidité des mouvements.

Dans notre système, un driver A4988 est associé à chaque axe motorisé du Puzzle Bot. Leur utilisation permet d'obtenir un positionnement précis tout en limitant la complexité du programme de commande.

Le choix du A4988 repose sur sa compatibilité avec le CNC Shield V3, sa simplicité de mise en œuvre et sa capacité à fournir un contrôle précis des moteurs pas à pas.

<img width="565" height="517" alt="image" src="https://github.com/user-attachments/assets/9550ba87-f22c-478a-9532-ec8f8b30a31d" />


