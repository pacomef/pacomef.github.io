---
title: Divine Journey
tag: project
order: 7
summary: A personal project — details to come.
link_label: details
link_url: "#"
photos:
  - "/_images/dj2/quest_alchemistry.png"
  - "/_images/dj2/craft_philosopher.png"
  - "/_images/dj2/integrated_dynamics.png"
---

<div class="summary-box" markdown="1">
Résumé si pressé:
- J'ai passé énormément d'heures à compléter un jeu, basé sur Minecraft, qui requiert une vraie réflexion continue, et une automatisation totale.
- Les quantittés d'objets nécessaire à la complétion du jeu sont énormes et c'est principalement un défi logistique.
- La plupart des personnes tentant le jeu abandonnent après avoir été bloqué suite à un manque d'automatisation.
</div>

Divine Journey est un "expert modpack" sur Minecraft. Le principe est de modifier très lourdement minecraft pour y ajouter des centaines de machines, de matériaux, des composés chimiques, de la sorcellerie, de l'electricité, des planètes, des ennemis. Chaque "mod" peut vivre indépemendament des autres, mais un modpack les fait intéragir, pour mêler la manière dont certains objets sont crées.

Divine Journey 2 est un modpack "linéaire", qui se base sur des quêtes (+1600), divisés en 30 chapitres, et chaque chapitre doit avoir été majoritairement complété pour pouvoir passer au suivant. Il y a donc des âges de civilisation que l'on peut atteindre, l'un après l'autre.

Exemple d'un arbre de quête pour le chapitre se concentrant sur les procédés chimiques:

![Arbre de quêtes du chapitre alchimie]({{ "/_images/dj2/quest_alchemistry.png" | relative_url }})
{: .img-wrap}

Chaque quête correspond à peu de choses près à l'obtention d'un objet, qui se construit à l'aide des objets précédents. Et dans chaque chapitre, disons qu'il est nécessaire d'utiliser environ 2 fois l'objet final du chapitre précédent, pour faire l'objet final de ce chapitre (en passant par d'innombrables machine!). Cela fait donc environ 2**29 = 1/2 milliard d'objets nécessaire pour atteindre le dernier chapitre, qui n'en n'a alors plus rien à faire et multiplie toutes les quantités demandé par presque un millier.

Voici un objet créé vers les derniers chapitres, qui en consomme des dizaines d'autres, par exemple:

![Craft de fin de partie consommant des dizaines d'objets]({{ "/_images/dj2/craft_philosopher.png" | relative_url }})
{: .img-wrap}

C'est donc, avant tout, un énorme défi logistique, il faut pouvoir:
- Générer de l'énergie, et l'apporter aux machines en ayant besoin, en sachant que toutes les machines ne reçoivent pas le même type d'énérgie
- Acheminer tous les objets d'une machine à une autre, pour que la machine puisse fonctionne automatiquement, et surtout: 24h/24, même quand le joueur n'est pas là pour régler les problèmes, mais que le serveur tourne
- Stocker tous les objets, et avoir un système pour obtenir un autre objet sur demande, car tous les objets ne valent pas la peine d'être automatisé en continu (ce qui requiert littéralement d'automatiser chaque étape des matières premières à l'objet final, imaginez faire cela ne serait-ce que pour une carte mère!).
- Accélérer encore et encore chaque processus, pour pouvoir satisfaire la demande qui ne fait que grossir de chapitre en chapitre!
- S'assurer que les matières premières tiennent le coup, et qu'elles ne sont pas plus vite consommés que récupérées.

À ces problème s'ajoute le lag, ie la charge sur le CPU du serveur, car même si le fait d'avoir 15 000 000 d'un objet A peut être réduit à un simple entier, le fait de devoir utiliser cet objet 15 000 000 de fois dans différentes machines est bien différent. Le nombre de machine nécessaires est ce qui fait toute la lourdeur de la tâche, car les machines gardent en mémoire quels objets elles contiennent, quel pourcentage de la tâche actuelle a été effectuée, et surtout elles interagissent avec les machines aux alentours, ce qui rajoute des listeners dans tous les sens. 

Voici un exemple de lag conséquent, auquel j'ai souvent du faire face: un millier d'objets sur le sol. Tout le texte indique le temps consommé par chaque objet, sur le CPU, durant un "tick" qui est l'unité temporelle de minecraft, correspondant à 0.05 secondes, lorsque le serveur n'a pas de problème à suivre la cadence. Tous ces objets sont sur le sol, car, à 2000 mètres de là, une machine s'est bloquée, car l'un des objets nécessaire à son fonctionnement n'était plus produit assez vite, par manque de ressources. Alors, l'autre objet qui y était inséré a commencé à ne plus être consommé, et le stockage de cet objet s'est saturé. Cela a fait une réaction en chaine, impactant tous les stockages précédants, et, au bout de 2 heures, tous ces objets se sont retrouvés sur le sol, où ils générent bien plus de lag, plutôt que dans le stockage qui était prévu pour eux, car saturé. 

![Un millier d'objets au sol générant du lag sur le serveur]({{ "/_images/dj2/lag.png" | relative_url }})
{: .img-wrap}

Le fait d'avoir énormément de cable est aussi très lourd pour le serveur, car un cable est autorisé à transporter plusieurs types d'objets, qui doivent alors savoir dans quelle machine se diriger, en fonction des filtres indiqués. 

Ce que je trouve magnifique malgré tout, c'est la liberté logistique donnée par ce genre de modpack. Minecraft est déjà Turing-complet, sans qu'on lui rajoute quoi que ce soit, et on peut y créer des ordinateurs simulant Tetris par exemple. Mais en rajoutant des mods, qui sont autant centrés sur l'industrialisation et la programmation, on en arrive très vite à avoir accès à des languages de programmation très littéraux.

La majorité de ceci est permis par Integrated Dynamics, qui permet de mesurer, manipuler, coder tout ce à quoi il est possible de penser. Les réseaux d'integrated dynamics possèdent autant d'instructions qu'il est en cité ici: https://integrateddynamics.rubensworks.net/book/manual/logic_programming.html.

![Réseau Integrated Dynamics lisant les attributs des plantes]({{ "/_images/dj2/integrated_dynamics.png" | relative_url }})
{: .img-wrap}

On peut y trouver des bitshifts, des foncteurs, des manière de mesurer la performance du CPU du serveur, la durée exacte depuis la dernière pluie (en millisecondes), et tellement plus. C'est une liberté permettant des systèmes infiniments complexes. Dans la photo juste au dessus, les cables bleus sont d'Integrated Dynamics, et ils servent à lire les attributs des plantes poussant au milieu du petit système, de vérifier si le jeu leur associe une métadonnée bien spécifique, et à récolter les plantes si cet attribut apparaît, pour récupérer un objet spécifique. Tout ceci à une vitesse phénoménale (mais limité pour ne pas trop augmenter le lag).

Tout ceci m'aura pris environ 700 heures, pour finir le jeu de A à Z. J'ai cru comprendre que beaucoup de personnes le finissaient en un peu moins de 1000 heures, je pense donc être parfaitement dans la moyenne. Beaucoup de personnes ne le finissent simplement pas car ils n'ont pas assez automatisé leur système, ce qui les pousse à des extrêmes pour des quêtes qui sont autrement plus simple avec de l'automatisation.