---
title: C Compiler
tag: project
order: 5
summary: A small compiler from C to assembly.
link_label: details
link_url: "#"
lang: en
permalink: /en/projects/c-compiler/
translation_url: /projects/c-compiler/
photos:
  - "/_images/c-compiler/C.png"
  - "/_images/c-compiler/ASM.png"
  - "/_images/c-compiler/python.png"
---

<div class="summary-box" markdown="1">
Quick summary:
- I built a C-to-assembly compiler that can handle every operation in the bullet list at the bottom of this page.

Repo: [github.com/pacomef/micro-c-compiler](https://github.com/pacomef/micro-c-compiler)
</div>

When I arrived at Télécom Paris, we had a group project early in the year, aiming to reproduce the behavior of a C compiler and a python interpreter.

On my side, I built the compiler in python, as well as the interpreter. I preferred python's flexibility to venture into a domain I didn't know at all.

As for the compiler, which is the biggest part of the project, the code can be found at: https://github.com/pacomef/micro-c-compiler/blob/main/FinalProjectPy/core.py, 1400 lines of python code.

This code (together with the parser) can compile the following:
- Declaration of global variables, global arrays, ...
- Declaration of functions with as many parameters as needed
- Types: int, bool, pointers to any type, at any level of indirection (int**, etc)
- Arrays of arbitrary dimension, implemented as pointers to pointers
- Declaration of variables without a value
- Pointers: &x, (also works for &a[i]), *x (usable as *x = 5), and pointer arithmetic
- Operations: +, -, /, *, %, &, |, ^, &&, ||, <, >, <=, >=, ==, !=, ! (unary), - (unary)
- Loops: if, if/else, while, for, break, continue
- Return (with or without a value)
- Use of a stack for functions
