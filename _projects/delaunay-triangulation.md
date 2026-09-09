---
title: Delaunay Triangulation in Pure C
tag: project
order: 4
summary: A Delaunay triangulation algorithm implemented in pure C, no external libraries.
link_label: details
link_url: "#"
photos:
  - "/_images/delaunay/aurora_rings.png"
  - "/_images/delaunay/kaleidoscope_mandala.png"
  - "/_images/delaunay/sunset_spiral.png"
---

<div class="summary-box" markdown="1">
Résumé si pressé:
- J'ai implementé une version de l'algorithme de Bowyer-Watson, servant à créer une triangulation de Delaunay.
- Le code a été fait entièrement en C pur (et en python pour faire les rendus visuels).
- J'ai utilisé une structure de R-arbre pour trouver les points à l'intérieur d'un espace en temps logarithmique.
- J'en ai implementé une version en O(n log n), en trouvant les bonnes structures de données, pour monter jusqu'à plusieurs millions de points, là où la version "classique" marche en O(n^2).

Repo: [github.com/pacomef/delaunay-triangulation](https://github.com/pacomef/delaunay-triangulation)
</div>

Lors de ma deuxième année de prépa, il fallait préparer un projet pour les concours d'ingénieur. Avec deux de mes amis, nous avons choisis de travailler sur la triangulation de delaunay, tous sur un aspect différent: les mathématiques, l'algorithmie, et la physique.

Je me suis occupé du côté algorithmique, qui consistait "simplement" à implémenter cette dite triangulation de Delaunay, et à pouvoir renvoyer à mes amis une triangulation d'un ensemble de points qu'ils me donneraient.

Pour certaines de nos expériences, notamment pour mon ami travaillant en physique, il fallait pouvoir monter à 5 000 000 de points idéalement. Il fallait donc une complexité adapté (O(n) ou O(n log n)), et la plupart des algorithmes présentés ne tournaient malheureusement qu'en O(n^2). 

Il y avait deux choix principaux pour essayer de baisser la complexité:
- L'algorithme de Bowyer-Watson, qui marche de manière incrémentale, en corrigeant rapidement la triangulation précédente.
- Un algorithme de diviser pour régner.

L'algorithme de diviser pour régner nous a semblé expliqué trop légérement dans les papiers que nous avons réussi à trouver, donc j'ai décidé de travailler sur l'algorithme de Bowyer-Watson. C'est un algorithme relativement bien connu, mais en vérité peu de personnes détaillent les structures de données utilisées en pratique.

En plus de cela, tout le projet a été réalisé en C pur, et il a été une règle d'or de n'avoir aucune fuite de mémoire.

Il a donc fallu inférer quelles informations étaient nécessaire et comment faire tourner chaque ligne d'un pseudo code un peu évasif, car aucun des papiers de recherche que nous avons trouvé ne détaillait cela non plus. La structure la plus lourde utilisée est celle de R-arbre, qui permettent de trouver rapidement quels points sont présents dans une région donnée de l'espace. Ensuite, il faut surtout faire en sorte que chaque triangle, segment, point, etc ait autant d'information que possible sur ce qu'il l'entoure.

Rajoutez à cela énormément de debug (et un peu de python pour la visualisation), et vous pourrez obtenir les images suivantes:

<div class="carousel">
<div class="carousel-track">
<img src="{{ '/_images/delaunay/aurora_rings.png' | relative_url }}" alt="Triangulation de Delaunay - Aurora rings">
<img src="{{ '/_images/delaunay/candy_cloud.png' | relative_url }}" alt="Triangulation de Delaunay - Candy cloud">
<img src="{{ '/_images/delaunay/coral_reef.png' | relative_url }}" alt="Triangulation de Delaunay - Coral reef">
<img src="{{ '/_images/delaunay/disco_grid.png' | relative_url }}" alt="Triangulation de Delaunay - Disco grid">
<img src="{{ '/_images/delaunay/dune_terrain.png' | relative_url }}" alt="Triangulation de Delaunay - Dune terrain">
<img src="{{ '/_images/delaunay/golden_sunflower.png' | relative_url }}" alt="Triangulation de Delaunay - Golden sunflower">
<img src="{{ '/_images/delaunay/kaleidoscope_mandala.png' | relative_url }}" alt="Triangulation de Delaunay - Kaleidoscope mandala">
<img src="{{ '/_images/delaunay/lava_lamp.png' | relative_url }}" alt="Triangulation de Delaunay - Lava lamp">
<img src="{{ '/_images/delaunay/molten_core.png' | relative_url }}" alt="Triangulation de Delaunay - Molten core">
<img src="{{ '/_images/delaunay/northern_curtain.png' | relative_url }}" alt="Triangulation de Delaunay - Northern curtain">
<img src="{{ '/_images/delaunay/stained_glass.png' | relative_url }}" alt="Triangulation de Delaunay - Stained glass">
<img src="{{ '/_images/delaunay/stardust_field.png' | relative_url }}" alt="Triangulation de Delaunay - Stardust field">
<img src="{{ '/_images/delaunay/sunset_spiral.png' | relative_url }}" alt="Triangulation de Delaunay - Sunset spiral">
</div>
</div>

Voici également un petit aperçu de la complexité, et du temps d'éxecution:

![Graphe des technologies utilisées par le bot]({{ "/_images/delaunay/complexity.png" | relative_url }})
{: .img-wrap}