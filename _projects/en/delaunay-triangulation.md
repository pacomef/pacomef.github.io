---
title: Delaunay Triangulation in Pure C
tag: project
order: 4
summary: A Delaunay triangulation algorithm implemented in pure C, no external libraries.
link_label: details
link_url: "#"
lang: en
permalink: /en/projects/delaunay-triangulation/
translation_url: /projects/delaunay-triangulation/
photos:
  - "/_images/delaunay/aurora_rings.png"
  - "/_images/delaunay/stained_glass.png"
  - "/_images/delaunay/coral_reef.png"
---

<div class="summary-box" markdown="1">
Quick summary:
- I implemented a version of the Bowyer-Watson algorithm, used to build a Delaunay triangulation.
- The code was written entirely in pure C (and a bit of python for the visual renders).
- I used an R-tree structure to find points inside a region of space in logarithmic time.
- I implemented an O(n log n) version, by finding the right data structures, allowing it to scale up to several million points, where the "classic" version runs in O(n^2).

Repo: [github.com/pacomef/delaunay-triangulation](https://github.com/pacomef/delaunay-triangulation)
</div>

During my second year of classes préparatoires, we had to prepare a project for the engineering school entrance exams. With two of my friends, we chose to work on Delaunay triangulation, each of us tackling a different angle: mathematics, algorithmics, and physics.

I took care of the algorithmic side, which "simply" consisted of implementing said Delaunay triangulation, and being able to return a triangulation of a set of points given by my friends.

For some of our experiments, especially for my friend working on the physics side, we ideally needed to scale up to 5,000,000 points. That required a suitable complexity (O(n) or O(n log n)), and unfortunately most of the algorithms out there only ran in O(n^2).

There were two main options to try to lower the complexity:
- The Bowyer-Watson algorithm, which works incrementally, quickly fixing up the previous triangulation.
- A divide-and-conquer algorithm.

The divide-and-conquer algorithm seemed too lightly explained in the papers we managed to find, so I decided to work on the Bowyer-Watson algorithm instead. It's a relatively well-known algorithm, but in truth very few people go into detail about the data structures actually used in practice.

On top of that, the whole project was written in pure C, and it was a golden rule to have zero memory leaks.

So I had to work out which information was actually needed and how to translate each line of a somewhat vague pseudo-code, since none of the research papers we found detailed that either. The heaviest structure used is an R-tree, which makes it possible to quickly find which points lie within a given region of space. Beyond that, the main challenge is making sure every triangle, edge, point, etc. carries as much information as possible about what surrounds it.

Add to that a huge amount of debugging (and a bit of python for visualization), and you get the following images:

<div class="carousel">
<div class="carousel-track">
<img src="{{ '/_images/delaunay/aurora_rings.png' | relative_url }}" alt="Delaunay triangulation - Aurora rings">
<img src="{{ '/_images/delaunay/candy_cloud.png' | relative_url }}" alt="Delaunay triangulation - Candy cloud">
<img src="{{ '/_images/delaunay/coral_reef.png' | relative_url }}" alt="Delaunay triangulation - Coral reef">
<img src="{{ '/_images/delaunay/disco_grid.png' | relative_url }}" alt="Delaunay triangulation - Disco grid">
<img src="{{ '/_images/delaunay/dune_terrain.png' | relative_url }}" alt="Delaunay triangulation - Dune terrain">
<img src="{{ '/_images/delaunay/golden_sunflower.png' | relative_url }}" alt="Delaunay triangulation - Golden sunflower">
<img src="{{ '/_images/delaunay/kaleidoscope_mandala.png' | relative_url }}" alt="Delaunay triangulation - Kaleidoscope mandala">
<img src="{{ '/_images/delaunay/lava_lamp.png' | relative_url }}" alt="Delaunay triangulation - Lava lamp">
<img src="{{ '/_images/delaunay/molten_core.png' | relative_url }}" alt="Delaunay triangulation - Molten core">
<img src="{{ '/_images/delaunay/northern_curtain.png' | relative_url }}" alt="Delaunay triangulation - Northern curtain">
<img src="{{ '/_images/delaunay/stained_glass.png' | relative_url }}" alt="Delaunay triangulation - Stained glass">
<img src="{{ '/_images/delaunay/stardust_field.png' | relative_url }}" alt="Delaunay triangulation - Stardust field">
<img src="{{ '/_images/delaunay/sunset_spiral.png' | relative_url }}" alt="Delaunay triangulation - Sunset spiral">
</div>
</div>

Here's also a small overview of the complexity, and the running time:

![Graph of the technologies used by the bot]({{ "/_images/delaunay/complexity.png" | relative_url }})
{: .img-wrap}
