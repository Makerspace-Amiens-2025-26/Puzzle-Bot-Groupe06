# Etape 3: PROGRAMMATION & VISION
### Programme de contrôle moteurs pas à pas

Le déplacement de notre Puzzle Bot est assuré par trois moteurs pas à pas commandés par une carte Arduino Uno via un CNC Shield équipé de drivers A4988. Le programme présenté ci-dessous a pour objectif de vérifier le bon fonctionnement des axes X, Y et A en réalisant un déplacement synchronisé des trois moteurs.

<pre>
// Axe X
#define X_STEP 2
#define X_DIR  5

// Axe Y
#define Y_STEP 3
#define Y_DIR  6

// Axe A
#define A_STEP 12
#define A_DIR  13

// Activation des drivers
#define ENABLE 8

// Vitesse de déplacement (µs)
#define VITESSE 1000

void setup()
{
    pinMode(X_STEP, OUTPUT);
    pinMode(X_DIR, OUTPUT);

    pinMode(Y_STEP, OUTPUT);
    pinMode(Y_DIR, OUTPUT);

    pinMode(A_STEP, OUTPUT);
    pinMode(A_DIR, OUTPUT);

    pinMode(ENABLE, OUTPUT);

    // Activation des drivers A4988
    digitalWrite(ENABLE, LOW);

    // Définition du sens de rotation
    digitalWrite(X_DIR, HIGH);
    digitalWrite(Y_DIR, HIGH);
    digitalWrite(A_DIR, HIGH);
}

void loop()
{
    // Déplacement simultané des trois axes
    for (int i = 0; i < 2000; i++)
    {
        digitalWrite(X_STEP, HIGH);
        digitalWrite(Y_STEP, HIGH);
        digitalWrite(A_STEP, HIGH);

        delayMicroseconds(5);

        digitalWrite(X_STEP, LOW);
        digitalWrite(Y_STEP, LOW);
        digitalWrite(A_STEP, LOW);

        delayMicroseconds(VITESSE);
    }

    // Arrêt du programme
    while (1);
}
</pre>

Dans ce programme, les broches de commande **STEP** et **DIR** de chaque axe sont définies conformément au câblage du CNC Shield. Les drivers sont activés grâce à la broche **ENABLE**, configurée à l'état bas (LOW). Le sens de rotation des moteurs est ensuite fixé à l'aide des signaux **DIR**.

La boucle principale génère simultanément 2000 impulsions sur les broches **STEP** des trois axes. Chaque impulsion provoque l'avancement d'un pas moteur, ce qui permet d'obtenir un mouvement synchronisé des axes X, Y et A. La variable **VITESSE** détermine le délai entre deux impulsions et permet ainsi de régler la vitesse de déplacement des moteurs.

### Programme de Contrôle du système de préhension pneumatique

Le système de préhension de notre Puzzle Bot repose sur une pompe à air et une électrovanne pilotées par la carte Arduino Uno. Le programme présenté ci-dessous nous a permis de tester individuellement le fonctionnement de ces deux actionneurs afin de vérifier la génération et la libération de la dépression utilisée pour la saisie des pièces.

<pre>
#define PUMP  12
#define SOL   13

void setup() {
  pinMode(PUMP, OUTPUT);
  pinMode(SOL,  OUTPUT);
}

void loop() {

  // 1. Pompe ON
  digitalWrite(PUMP, HIGH);
  delay(2000);

  // 2. Pompe OFF
  digitalWrite(PUMP, LOW);
  delay(1000);

  // 3. Electrovanne ON
  digitalWrite(SOL, HIGH);
  delay(2000);

  // 4. Electrovanne OFF
  digitalWrite(SOL, LOW);
  delay(1000);

}

</pre>

Dans ce programme, la pompe à air est connectée à la broche numérique **12** de l'Arduino tandis que l'électrovanne est connectée à la broche numérique **13**. Après l'initialisation des broches en sortie, la boucle principale exécute une séquence de test automatique.

La pompe est d'abord activée pendant deux secondes afin de créer une dépression dans le circuit pneumatique. Elle est ensuite arrêtée pendant une seconde. L'électrovanne est alors activée pendant deux secondes pour libérer la dépression et provoquer le relâchement de la pièce. Enfin, l'électrovanne est désactivée pendant une seconde avant que le cycle ne recommence.

###  Les tags Aruco — Principe et rôle dans le projet

Les tags Aruco sont des marqueurs visuels carrés composés d'une **bordure noire distincte** et d'une **matrice interne de pixels binaires** (noirs ou blancs), formant un code unique identifiable par un algorithme de détection. Leur conception a été pensée pour être robuste aux variations d'éclairage, de distance et d'angle de vue, ce qui en fait un choix particulièrement adapté aux applications de vision par ordinateur en temps réel.

Dans le cadre de notre projet Puzzle Bot, les tags Aruco sont utilisés pour **localiser les pièces du puzzle** dans le champ de la caméra. Chaque tag est associé à un identifiant numérique unique, ce qui permet au système de distinguer les différentes pièces et de déterminer leur position dans l'espace de travail.

###  Matériel utilisé

La détection est assurée par une **caméra à port USB**, positionnée au-dessus du plateau de travail de manière à couvrir l'ensemble de la zone où sont déposées les pièces du puzzle. Elle est connectée directement à l'ordinateur qui exécute le script Python de traitement d'image.


###  Implémentation Python — Détection des tags Aruco

Le traitement d'image est réalisé en **Python**, en s'appuyant sur les bibliothèques **OpenCV** et son module **aruco**. Le script capture le flux vidéo en temps réel depuis la caméra USB, analyse chaque image et y détecte les tags Aruco présents.

Le fonctionnement du code suit les étapes suivantes :

**Capture du flux vidéo**: La caméra est initialisée via OpenCV, qui capture les images frame par frame en continu.

**Détection des marqueurs**: Chaque image est analysée par la fonction de détection Aruco, qui recherche les contours carrés caractéristiques des marqueurs et décode leur matrice binaire interne pour en extraire l'identifiant.

**Affichage des résultats** — Lorsqu'un tag est détecté, plusieurs éléments visuels sont superposés à l'image en temps réel :
- Le **contour du tag est entouré en vert**, confirmant visuellement la détection.
- L'**identifiant numérique du tag** est affiché à proximité du marqueur.
- Un **carré rouge est placé sur le coin supérieur gauche** du tag, indiquant le point de référence de position retenu pour ce marqueur.

**Extraction des coordonnées** — Les coordonnées pixel du tag détecté sont extraites et peuvent être transmises au reste du système pour calculer la position réelle de la pièce sur le plateau.
