---
title: Project Euler
tag: project
order: 2
summary: Working through Project Euler's math and programming problems.
link_label: repo
link_url: "#"
---

Résumé si pressé:
- Project Euler est un site d'algorithmie spécialisé en mathématiques.
- Le site compte un million d'inscrits et je me classe actuellement 560 mondial avec 455 problèmes résolus. 
- Je suis rentré depuis quelques mois dans l'équipe du site, et j'aide à prendre des décisions sur la direction du site (notamment face à la montée de l'IA).
- Pour résoudre autant de problème, j'ai du passer beaucoup de temps à lire des papiers de recherche, et à implémenter leur méthodes, et j'ai énormément appris en théorie des nombres notamment.
- Pour Project Euler, je code beaucoup en python, Sage et CUDA (C++), en fonction des usages.

J'aime énormément Project Euler. Le site se concentre sur l'algorithmie, avec un aspect mathématique très important, que n'ont pas les autres sites de programmation compétitive. Le principe est simple: environ 1000 problèmes (1 publié par semaine depuis 2001), et une réponse textuelle à fournir.

Voici un exemple:

![Exemple de problème Project Euler]({{ "/_images/projecteuler.png" | relative_url }})
{: .img-wrap}

J'ai commencé à m'y attaquer en 2020, alors que j'avais 16 ans. Ce fut ma première grande découverte de l'algorithmie, et en vérité des mathématiques.

Au moment d'écrire ces lignes, j'ai 455 problèmes résolus sur les 1007 que compte le site. Ceci me place parmi les 560 premiers utilisateurs du site, sur environ un million d'inscrits (soit les premiers 0.06%). C'est un bel accomplissement, mais je suis surtout heureux de me rendre compte tout ce que j'y ai appris. 

Les problèmes étant majoritairement tous très différents, il y a presque autant de techniques et d'algorithmes que j'ai du découvrir/apprendre que de problèmes (Tonelli Shanks, Berlekamp Massey, Hermite Serret, Algorithme de Gosper, Miller Rabin, ...). Les techniques les plus avancées que j'ai dû toucher gravitent autour de la théorie analytique des nombres (par exemple: trouver \sum_{i=1}^n phi(i) en temps sous linéaire (phi étant l'indicatrice d'Euler)).

J'ai d'abord commencé Project Euler en C++ (lorsque j'avais 16 ans), car c'était le langage principal que j'utilisais pour la programmation compétitive. Mais lors des 3 dernières années, je suis petit à petit passé à Python car le défi principal des problèmes sont les mathématiques, et python aide beaucoup à tester rapidement des petits cas. J'utilise aussi Sage depuis un an, pour des problèmes un peu spécifique impliquant des corps finis ou autre joyeuseté, lorsque les méthodes ne peuvent pas être répliqué en 3 lignes en python (par exemple: trouver le noyeau d'une matrice dans F_2). J'utilise toujours CUDA si des problèmes sont trop facilement parallèlisables, et que je ne vois pas la "bonne" solution.

