---
---
layout: home
nav_order: 1
title: Accueil
permalink: /
---
---

# Bienvenue sur notre documentation

Bienvenue sur la documentation technique de notre Puzzle Bot, projet réalisé dans le cadre de notre cursus d'ingénierie au MakerSpace d'UniLaSalle Amiens (2025–2026). Ce site a pour but de fournir toutes les informations nécessaires pour comprendre, reproduire et améliorer notre machine.

[Notre projet sur Onshape]https://cad.onshape.com/documents/5e631fda2e1ceae9c0462f93/w/d6b894d752c92886e042732c/e/e8dc96c274546d67ed3770eb?renderMode=0&uiState=6a2d15bd71605c37b024c89c{: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
[Notre repo GitHub](https://github.com/Makerspace-Amiens/template-project){: .btn .fs-5 .mb-4 .mb-md-0 }

<iframe height="600" width="100%" src="https://modelembedder.net/embed?did=2860ed3d58f1b518e6857770&wvm=v&wvmid=6280fca954e7770df59e5a2f&eid=0cab16137cd459ee83ebe56e&elementType=ASSEMBLY" frameborder="0"></iframe>

{: .warning }
>Pour intégrer la visualisation de votre projet Onshape, utilisez le site https://modelembedder.net . Activez le partage par lien via l'outil de partage de Onshape. n'oubliez pas d'activer l'option "export". Puis completez l'iframe ci-dessus avec le lien généré par le site https://modelembedder.net. Vous pouvez mettre à jour également le bouton avec le lien de partage de votre modèle.


## À propos du Projet
Le Puzzle Bot est une machine autonome capable d'assembler un puzzle à pièces (jigsaw) sans aucune intervention humaine. Elle repose sur une architecture cartésienne à trois axes (X, Y, A), pilotée par une carte Arduino Uno associée à un CNC Shield. La détection et la localisation des pièces sont assurées par vision par ordinateur, grâce à des tags Aruco et une caméra USB traitée en Python via OpenCV. La saisie des pièces est réalisée par un système pneumatique composé d'une pompe, d'une électrovanne et d'une ventouse.
Ce projet s'adresse à tout ingénieur ou maker souhaitant concevoir une machine automatisée combinant mécanique, électronique, logiciel embarqué et vision artificielle. Notre documentation a été rédigée pour être suffisamment claire et détaillée afin qu'une équipe tierce puisse reproduire ou améliorer le système à partir des sources fournies.

## L'équipe — Groupe 06
- ## Conception et Prototypage: Yacine Benhedia et Anass Zahti
- ## Programmation et montage électronique: Alladaye Daril et Georges-Henri Nechie Gadom
- ## Vision par Ordinateur: Nicolas Huguenot et Abdelhamid Tissir

Notre documentation est organisée en trois grandes parties correspondant aux phases de développement de notre projet :

Étape 1 — Conception mécanique : modélisation de la structure cartésienne sous Onshape, choix des profilés aluminium 20x20, fabrication des pièces par impression 3D et découpe laser.

Étape 2 — Montage électronique : câblage de l'Arduino Uno, du CNC Shield et des drivers A4988, pilotage du système pneumatique via le driver L9110.

Étape 3 — Programmation & Vision : implémentation Python avec OpenCV pour la détection des tags Aruco, extraction des coordonnées et communication série avec l'Arduino.

## Poster

<img width="2000" height="1414" alt="Poster-Groupe6" src="https://github.com/user-attachments/assets/cbd68453-8ac6-4647-8e1a-5a5c17a2ab68" />


## Vidéo

Ici vous publierez la vidéo de votre projet. 
- 1min30 au format vertical
- Présentation du projet 
- Des explication du fonctionnement du projet
- Des vues du projet / Prototype / Application etc... 
- Des plans du fonctionnement (même basique ou des éléments séparés)
- Une conclusion
- Si en stockage local : <50mo

<video src="images/intro_amiens.mp4" controls title="Title"  style="width: 100%;"></video>

---
