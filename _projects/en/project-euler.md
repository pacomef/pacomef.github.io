---
title: Project Euler
tag: project
order: 2
summary: Working through Project Euler's math and programming problems.
link_label: details
link_url: "#"
lang: en
permalink: /en/projects/project-euler/
translation_url: /projects/project-euler/
photos:
  - "https://projecteuler.net/profile/pacome_f.png"
  - "https://projecteuler.net/resources/images/0453_quad.png"
  - "https://projecteuler.net/resources/images/0671_loop_acceptable.png"
---

<div class="summary-box" markdown="1">
Quick summary:
- Project Euler is an algorithmic problem site focused on mathematics.
- The site has a million registered users and I'm currently ranked 560th worldwide with 455 problems solved.
- I joined the site's (small) team a few months ago, and I help make decisions about the site's direction (notably in the face of the rise of AI).
- To solve that many problems, I've had to spend a lot of time reading research papers and implementing their methods, and I've learned an enormous amount about number theory in particular.
- For Project Euler, I code a lot in python, Sage, and CUDA (C++), depending on the use case.
</div>

<span class="underline">Introduction:</span> I really love Project Euler. The site focuses on algorithmics, with a very strong mathematical component that other competitive programming sites don't have. The idea is simple: about 1000 problems (one published per week since 2001), and a text answer to provide.

Here's an example (a very, very simple one):

![Example Project Euler problem]({{ "/_images/projecteuler/problem1.png" | relative_url }})
{: .img-wrap}

I started tackling it in 2020, when I was 16. It was my first big discovery of algorithmics, and honestly of mathematics itself.

<span class="underline">Progress:</span> As I'm writing this, I have 455 problems solved out of the 1007 the site has. That puts me among the top 560 users on the site, out of about a million registered users (the top 0.06%). It's a nice achievement, but I'm mostly happy realizing everything I've learned along the way.

Since the problems are mostly all very different from one another, there are almost as many techniques and algorithms I've had to discover or learn as there are problems (Tonelli-Shanks, Berlekamp-Massey, Hermite-Serret, Gosper's algorithm, Miller-Rabin, ...). The most advanced techniques I've had to touch revolve around analytic number theory (for example: finding \sum_{i=1}^n phi(i) in sublinear time, phi being Euler's totient function).

<span class="underline">Language:</span> I first started Project Euler in C++ (when I was 16), since that was the main language I used for competitive programming. But over the last 3 years, I gradually switched to Python, since the main challenge in these problems is the mathematics, and python makes it much easier to quickly test small cases. I've also used Sage for about a year, for problems that are a bit more specific, involving finite fields or other such niceties, when the methods can't be replicated in 3 lines of python (for example: finding the kernel of a matrix over F_2). I use CUDA when a problem is too easily parallelizable and I can't see the "right" solution.

<span class="underline">Working on the site:</span> Since July 2026, I've joined the site's management team. My main role is to take part in discussions about the systems the site uses, whether it's the difficulty system, the "trust" granted to each user, or more recently the group system, similar to what Advent of Code offers.
