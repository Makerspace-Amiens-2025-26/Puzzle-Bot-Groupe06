---
layout: default
nav_order: 3
title: Objectifs du projet
---

# Introduction
Étudiants en troisième année à l’école d’ingénieurs UniLaSalle Amiens, nous avons été amenés à réaliser un projet de robotique: "Puzzle Bot" pour notre module de projet Multidisciplinaire. Notre projet « Puzzle Bot » a pour objectif de concevoir, fabriquer et mettre en service une machine capable de résoudre un puzzle de manière autonome. À travers cette réalisation, ce projet nous a permis de mobiliser des compétences en CAO, fabrication numérique, programmation, électronique, assemblage, calibration et vision par ordinateur.

Mené sur une durée totale de 75 heures au MakerSpace, il s’inscrit dans une démarche d’ingénierie complète : analyse du besoin, recherche de solutions, prototypage, tests, itérations et validation finale. Il constitue une continuité des projets précédents autour des machines de dessin, tout en introduisant une approche plus rigoureuse et plus ambitieuse de la conception d’un système automatisé.

Cette documentation technique présente les choix retenus, l’organisation du travail, les étapes de développement ainsi que l’état d’avancement du projet. Elle a également pour but de servir de référence afin de comprendre, reproduire et améliorer la machine dans une logique de transmission et de réutilisation.



## Contexte du Projet

Notre projet Puzzle Bot s’inscrit dans le cadre de notre formation d’ingénieur orientée dans les spécialisations de systèmes numériques et énergétiques. Constitué en équipes de six étudiants nous avons été organisé en sous équipes de binômes répartis en trois domaine de compétences à savoir: Conception assistée par Ordinateur et fabrication numérique, montage et programmation électronique et vision par ordinateur. Ce projet a constitué ainsi une opportunité pour nous de mettre en pratique nos compétences techniques, tout en développant l’autonomie, l’organisation et le travail en équipe.

## Objectifs du Projet

L'objectif principal de projet est de concevoir et réaliser une machine capable d'assembler automatiquement un puzzle à pièces (jigsaw), depuis la détection des pièces jusqu'à leur placement précis dans la configuration finale.

Cet objectif global se décline en plusieurs objectifs techniques :
-Détection et identification des pièces: Nous avons mis en œuvre un système de vision par ordinateur permettant de localiser chaque pièce du puzzle, d'analyser sa forme et son orientation, et de déterminer sa position cible dans l'assemblage final.

-Contrôle du mouvement: Nous avons développer un système de déplacement précis piloté par Arduino et CNC Shield, intégrant des moteurs pas à pas et servomoteurs pour assurer la saisie et le positionnement des pièces avec la fidélité requise.

-Conception et fabrication mécanique: Nous avons modéliser l'ensemble de la structure sous Onshape et fabriquer les pièces via impression 3D et découpe laser, en garantissant rigidité, répétabilité et facilité d'assemblage.

-Robustesse et fiabilité du système: Il s'agit pour nous de faire évoluer notre Proof of Concept (POC) initial vers une version finale stable, capable de fonctionner de manière autonome et continue sans défaillance lors de la démonstration.

-Documentation et transmissibilité: La production de notre documentation technique suffisamment claire et détaillée pour qu'une équipe tierce puisse reproduire ou améliorer la machine à partir des sources fournies


# Existant

Avant d'engager notre conception, une analyse des projets existants a été conduite afin d'identifier les approches techniques déjà éprouvées dans le domaine de la résolution automatisée de puzzles. Plusieurs réalisations notables ont servi de référence grâce au site internet du Makerspace:

-Mark Rober et Stuff Made Here ont tous deux développé des machines de résolution de puzzles combinant vision par ordinateur, bras cartésien et algorithmes de correspondance de formes. Ces projets illustrent la faisabilité de l'approche et les compromis à trouver entre vitesse d'exécution et précision de placement.

-Les machines CNC à base d'Arduino ont constitier une base technique documentée et accessible, notamment via des projets open source utilisant le firmware GRBL, des CNC Shields et des moteurs pas à pas. Cette architecture a guidé nos choix en matière de contrôle de mouvement.

-Les bibliothèques de vision par ordinateur comme OpenCV ont offert des outils matures pour la détection de contours, la correspondance de formes et le calcul de transformations géométriques, et ont été adoptées comme socle logiciel pour la partie détection.

Ces références nous ont permis d'éviter de repartir de zéro et d'orienter rapidement les choix architecturaux de l'équipe.


# Cahier des Charges
Sur la base de l'analyse de l'existant et des objectifs définis, le cahier des charges de notre projet structure les exigences du système en trois catégories : fonctionnelles, techniques et de projet.

1- Contraintes fonctionnelles

La machine doit être capable de détecter et d'identifier les pièces du puzzle posées dans son aire de travail, avec un taux de reconnaissance correct d'au moins 90 % des pièces. Une fois une pièce identifiée, elle doit être saisie et positionnée avec une précision de placement inférieure à 2 mm en XY, afin de garantir un assemblage cohérent et fidèle à la configuration cible. L'ensemble de ce processus de la détection au placement, doit se dérouler de manière entièrement autonome, sans aucune intervention humaine après le lancement de la machine.

2- Contraintes techniques

Sur le plan du contrôle du mouvement, la commande des axes repose sur une carte Arduino associée à un CNC Shield et des drivers de moteurs pas à pas. La saisie des pièces est assurée par un mécanisme servo-motorisé. La structure mécanique est intégralement modélisée sous Onshape et fabriquée au MakerSpace, en recourant à l'impression 3D et à la découpe laser pour l'ensemble des pièces constitutives. Le traitement d'image est pris en charge côté ordinateur, via Python et OpenCV, et communique avec l'Arduino par liaison série pour transmettre les consignes de déplacement. Enfin, l'intégralité du code source est versionnée et hébergée sur le dépôt GitHub dédié au projet.

3- Contraintes de projet

Le développement s'inscrit sur une durée de 75 heures encadrées, réparties entre une phase de Proof of Concept de 25 heures et une phase de finalisation de 50 heures. La livraison finale comprendra une démonstration fonctionnelle lors de la Journée des Projets, accompagnée de notre documentation technique, des sources techniques déposées sur GitHub et d'une vidéo de présentation.


Nam dui ligula, fringilla a, euismod sodales, sollicitudin vel, wisi. Morbi auctor lorem non justo. Nam lacus libero, pretium at, lobortis vitae, ultricies et, tellus.
