### Difficultés rencontrées au cours du projet

Au cours de la réalisation du Puzzle Bot, notre équipe a été confrontée à plusieurs difficultés techniques et organisationnelles qui ont ralenti l'avancement du projet.

La première difficulté concernait la phase de conception mécanique. Aucun membre du groupe ne possédait une expérience significative dans l'utilisation du logiciel Onshape. Cette situation a entraîné de nombreuses erreurs lors de la conception des pièces. Plusieurs modèles se sont révélés inadaptés ou incorrects et ont dû être modifiés, voire entièrement redessinés, ce qui a occasionné une perte de temps importante.

Lors de l'intégration électronique, nous avons également rencontré des difficultés dans l'affectation des axes aux moteurs pas à pas. Initialement, les trois moteurs étaient connectés aux axes X, Y et Z du CNC Shield. Après plusieurs essais, nous avons constaté que les mouvements obtenus n'étaient pas correctement synchronisés. Afin de résoudre ce problème, nous avons finalement remplacé l'axe Z par l'axe A, ce qui a permis d'obtenir un fonctionnement plus cohérent avec l'architecture mécanique du robot.

Par ailleurs, nous n'avons pas réussi à intégrer les capteurs de fin de course dans le système. En effet, certaines pièces mécaniques nécessaires à leur fixation n'ont pas pu être réalisées à temps. Cette difficulté a également concerné le bouton d'arrêt d'urgence, dont l'intégration n'a pas pu être finalisée.

Nous avons également rencontré un problème lié à l'alimentation du système pneumatique. La carte Arduino utilisée délivrait une tension de 5 V pour les signaux de commande, tandis que la pompe et l'électrovanne nécessitaient une alimentation de 12 V pour fonctionner correctement. En conséquence, l'électrovanne ne pouvait pas être commandée convenablement avec le montage initial ce qui faisait que notre pompe ne pouvait que aspirer l'air mais pas relâcher. Cette situation nous a conduits à envisager la conception d'une nouvelle carte électronique avec le logiciel KiCad comportant des MOSFET(transistor) qui vont permettre de libérer une puissance de 12V pour actionner le moteur.

Enfin, des difficultés organisationnelles ont également impacté le projet. Les absences répétées de certains membres de l'équipe ainsi qu'un manque d'implication dans les différentes tâches ont considérablement réduit l'efficacité du travail collectif. Ces contraintes, combinées aux problèmes techniques rencontrés, n'ont malheureusement pas permis d'achever complètement le projet dans les délais impartis.

