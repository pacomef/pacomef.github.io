---
title: C Compiler
tag: project
order: 5
summary: Un petit compilateur du C vers l'assembleur.
link_label: details
link_url: "#"
lang: fr
translation_url: /en/projects/c-compiler/
photos:
  - "/_images/c-compiler/C.png"
  - "/_images/c-compiler/ASM.png"
  - "/_images/c-compiler/python.png"
---

<div class="summary-box" markdown="1">
Résumé si pressé:
- J'ai réalisé un compilateur C vers assembleur, qui peut réaliser toutes les opérations de la bullet list en bas de cette page. 

Repo: [github.com/pacomef/micro-c-compiler](https://github.com/pacomef/micro-c-compiler)
</div>

À mon arrivée à Télécom Paris, nous avons eu un projet de groupe à faire durant le début de l'année, avec pour but de reproduire le comportement d'un compilateur C et d'un interpréteur python.

De mon côté, j'ai réalisé le compilateur en python, tout comme l'interpréteur. J'ai préféré la flexibilité de python pour m'aventurer dans un domaine que je ne connaissais pas du tout. 

Pour ce qui est du compilateur, qui représente la plus grosse partie du projet, le code peut être trouvé à: https://github.com/pacomef/micro-c-compiler/blob/main/FinalProjectPy/core.py, 1400 lignes de code en python.

Ce code (avec le parser) permet de compiler les choses suivantes:
- Déclaration de variables globales, de tableaux globaux, ...
- Déclaration de fonctions avec autant de paramètres que voulu
- Types: int, bool, pointeurs vers n'importe quel type, à n'importe quel niveau d'indexation (int**, etc)
- Tableaux de dimension quelconque, implementés comme pointeurs de pointeurs
- Déclaration de variables sans valeur
- Pointeurs: &x, (marche même pour &a[i]), *x (peut être utilisé comme *x = 5), et arithmétique des pointeurs
- Opérations: +, -, /, *, %, &, |, ^, &&, ||, <, >, <=, >=, ==, !=, ! (unaire), - (unaire)
- Boucles: if, if/else, while, for, break, continue
- Return (avec ou sans valeur)
- Pour les fonctions, utilisation d'une stack