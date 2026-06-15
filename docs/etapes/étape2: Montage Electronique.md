# Etape 2: montage électronique

### Vue d'ensemble du système

Notre système électronique du Puzzle Bot s'articule autour d'une **carte Arduino Uno** centrale, qui orchestre l'ensemble des actionneurs de la machine. Elle communique avec un **CNC Shield** empilé directement sur ses broches, lequel reçoit trois **drivers A4988**, un par axe chargés de traduire les signaux de commande en impulsions électriques pour les moteurs pas à pas. L'alimentation de l'ensemble est assurée par une **alimentation secteur**, qui fournit les tensions nécessaires à la fois à la logique de commande et à la puissance des actionneurs.

### 1. Alimentation du système

L'alimentation secteur fournit deux niveaux de tension :

- **5V**: pour l'alimentation logique de l'Arduino Uno et des composants de faible puissance (électrovanne, driver L9110).
- **12V**: pour l'alimentation puissance du CNC Shield, branché sur les bornes **GND** et **V+** prévues à cet effet sur le shield. Cette tension alimente directement les moteurs pas à pas via les drivers A4988.

  <img width="500" height="385" alt="image" src="https://github.com/user-attachments/assets/2aa46ec6-bcd7-429f-ab91-81796d16a08d" />



### 2. Assemblage Arduino Uno et CNC Shield

Le CNC Shield s'emboîte directement sur les broches de l'Arduino Uno. Une fois en place, les trois drivers A4988 sont insérés dans leurs emplacements respectifs sur le shield(la broche **EN** du driver alignée avec le marquage du shield). Les axes sont répartis comme suit :

- **Axe X** — premier driver, connecté au moteur pas à pas de l'axe horizontal principal.
- **Axe A** — deuxième driver, connecté au moteur pas à pas de l'axe horizontal secondaire.
- **Axe Y** — troisième driver, connecté au moteur pas à pas de l'axe vertical.

Chaque moteur pas à pas est relié à son driver via un connecteur 4 fils (bobines A+, A−, B+, B−), branché sur les bornes de sortie correspondantes du CNC Shield.

<img width="726" height="500" alt="image" src="https://github.com/user-attachments/assets/b5843833-8c42-429c-ae20-d6f245effb1e" />


### 3. Réglage des drivers A4988

Avant la mise en service, le courant de chaque driver A4988 sont calibré à l'aide d'un potentiomètre intégré, afin de ne pas dépasser le courant nominal des moteurs pas à pas utilisés. Ce réglage se fait en mesurant la tension de référence **Vref** sur la broche centrale du potentiomètre par rapport à la masse.

<img width="600" height="480" alt="image" src="https://github.com/user-attachments/assets/92b8832f-e911-44fe-adfe-2b9c1c519632" />


<img width="756" height="486" alt="image" src="https://github.com/user-attachments/assets/bd88ebb6-0657-47b6-a852-f4b27b047448" />


### 4. Câblage du système de préhension pneumatique

Le préhenseur pneumatique est piloté par deux composants distincts depuis l'Arduino :

**Pompe à air DC 4.5V**
La pompe est connectée aux sorties de la **carte driver L9110**, elle-même reliée à une broche PWM de l'Arduino (via le CNC Shield ou directement). Le L9110 joue le rôle d'interface de puissance, permettant à l'Arduino de commander la pompe sans risquer d'endommager ses sorties numériques. Les bornes d'alimentation du L9110 sont raccordées au 5V de l'alimentation secteur.

**Électrovanne 5V**
L'électrovanne est pilotée depuis une broche numérique de l'Arduino. Elle est alimentée en 5V depuis l'alimentation secteur. Lorsqu'elle est activée (ouverte), elle libère la dépression du circuit et provoque le relâchement de la pièce ; lorsqu'elle est fermée, la dépression est maintenue et la pièce reste saisie par la ventouse.

**Circuit pneumatique**
La pompe, l'électrovanne et la ventouse sont interconnectées par le tube souple, le raccord en T et le raccord droit. Le raccord en T distribue le flux d'air entre la pompe (qui génère la dépression), l'électrovanne (qui contrôle le relâchement) et la ventouse (qui assure le contact avec la pièce).

<img width="672" height="454" alt="image" src="https://github.com/user-attachments/assets/1528b2b5-9858-445d-9faf-0aa19f41f081" />



Pour assurer la communication entre la carte Arduino et les composants du Puzzle Bot, nous avons affecté des pins spécifiques à chaque élément. Le choix des pins a été fait en se référant à l’image suivante :

<img width="736" height="735" alt="image" src="https://github.com/user-attachments/assets/38c269d9-6d50-43cf-9409-35bff88f5497" />



