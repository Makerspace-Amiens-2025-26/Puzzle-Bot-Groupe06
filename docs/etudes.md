
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

# 4. Moteurs pas à pas

Les moteurs pas à pas constituent les principaux actionneurs mécaniques du Puzzle Bot. Contrairement à un moteur à courant continu classique, ils convertissent directement des impulsions électriques en déplacements angulaires précis.

Chaque impulsion envoyée par le driver provoque une rotation élémentaire du moteur appelée « pas ». Cette caractéristique permet un contrôle précis de la position sans nécessiter de système complexe de mesure de déplacement.

Dans notre machine, les moteurs pas à pas assurent les déplacements des différents axes de translation du robot. Ils permettent de positionner précisément la tête de préhension au-dessus des pièces du puzzle afin d'effectuer les opérations de saisie et de déplacement.

Leur utilisation a été privilégiée en raison de leur précision, de leur fiabilité et de leur excellente adéquation avec les applications de robotique et d'automatisation.

<img width="641" height="568" alt="Capture d&#39;écran 2026-06-01 175817" src="https://github.com/user-attachments/assets/32b532ef-b0b1-4eff-932c-3d47fd3eae5e" />


# 5. Driver moteur L9110

Le L9110 est un module de commande destiné aux moteurs à courant continu de faible puissance. Il intègre un pont en H permettant de contrôler l'alimentation du moteur et éventuellement son sens de rotation.

Dans le cadre du Puzzle Bot, ce module est utilisé pour piloter la mini-pompe à vide responsable de la génération de la dépression nécessaire au fonctionnement de la ventouse.

Le choix du L9110 est motivé par sa simplicité d'utilisation, sa compatibilité avec les sorties de l'Arduino et son faible coût. Il constitue une solution efficace pour le pilotage de petits moteurs fonctionnant sous basse tension.


<img width="250" height="200" alt="Capture d&#39;écran 2026-06-01 180053" src="https://github.com/user-attachments/assets/15955baa-bc39-4e4d-8d8f-af0d5053a02a" />


# 6. Pompe à vide DC 4,5 V

La pompe à vide est l'élément principal du système de préhension pneumatique. Son rôle consiste à aspirer l'air contenu dans le circuit afin de créer une dépression au niveau de la ventouse.

Lorsque la pompe est activée, elle extrait l'air du circuit pneumatique, ce qui provoque l'adhérence de la ventouse à la pièce du puzzle. Cette dépression permet ensuite de soulever et de transporter la pièce sans contact mécanique direct.

Cette solution a été retenue car elle permet de manipuler des pièces de formes variées sans nécessiter de système de pince complexe. Elle présente également l'avantage d'être légère, compacte et simple à intégrer à la structure du robot.

<img width="570" height="739" alt="Capture d&#39;écran 2026-06-01 180127" src="https://github.com/user-attachments/assets/6c9c391a-f63e-404f-b8ee-55aa3e6b9c72" />


# 7. Électrovanne 5 V

L'électrovanne est un dispositif électromécanique permettant de contrôler le passage de l'air dans le circuit pneumatique.

Dans notre système, elle intervient lors du relâchement des pièces. Lorsque l'électrovanne est activée, elle ouvre le circuit et annule la dépression créée par la pompe. La ventouse perd alors son pouvoir d'adhérence, ce qui permet de déposer la pièce à l'emplacement souhaité.

L'utilisation d'une électrovanne améliore considérablement la rapidité et la précision du relâchement par rapport à un simple arrêt de la pompe.

<img width="571" height="726" alt="Capture d&#39;écran 2026-06-01 180201" src="https://github.com/user-attachments/assets/d1346248-ca6a-4c93-97b3-d1f05413d357" />


# 8. Capteurs de fin de course

Les capteurs de fin de course sont utilisés pour détecter les positions limites des axes de déplacement de la machine. Ils permettent à l'Arduino de connaître la position de référence de chaque axe lors de la phase d'initialisation.

Au démarrage, les moteurs déplacent progressivement les chariots jusqu'à l'activation des capteurs. Cette procédure, appelée « homing », permet d'établir un repère commun à l'ensemble du système.

Les capteurs jouent également un rôle de sécurité en empêchant les axes de dépasser leurs limites mécaniques, ce qui pourrait entraîner des collisions ou des détériorations de la structure.

Leur intégration améliore ainsi la précision globale du système tout en augmentant sa fiabilité.

<img width="940" height="652" alt="image" src="https://github.com/user-attachments/assets/2fa25bc1-0fa6-4914-88c5-0d9aa7fe2133" />

# 9. Servomoteur

Le servomoteur est un actionneur capable de se positionner avec précision à un angle déterminé grâce à un système interne de contrôle.

Bien qu'il ne constitue pas l'élément principal de déplacement de notre robot, il peut être utilisé pour actionner certains mécanismes auxiliaires nécessitant un positionnement précis.

Son principal avantage réside dans sa facilité de commande depuis l'Arduino à l'aide d'un simple signal PWM, ainsi que dans sa précision de positionnement.

<img width="517" height="652" alt="image" src="https://github.com/user-attachments/assets/1b15bf22-09b6-4c49-aaa1-d085e4845169" />








