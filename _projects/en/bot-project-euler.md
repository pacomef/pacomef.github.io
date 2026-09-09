---
title: Bot Project Euler
tag: project
order: 3
summary: A project running 24/7 for 4 years now, with several thousand lines of code.
link_label: details
link_url: "#"
lang: en
permalink: /en/projects/bot-project-euler/
translation_url: /projects/bot-project-euler/
photos:
  - "/_images/pe-bot/discordlogo.png"
  - "/_images/pe-bot/workflow.png"
  - "/_images/pe-bot/statistics-pacome.png"
---

<div class="summary-box" markdown="1">
Quick summary:
- I run the Project Euler discord server, and I maintain a bot that tracks everyone's statistics in real time.
- It's a ~7000-line-of-code project, developed for about 4 years now.
- Data is fetched every minute, and I had to learn how to deploy services to keep the bot running continuously.

Repo: [github.com/pacomef/ProjectEulerBot](https://github.com/pacomef/ProjectEulerBot)
</div>



As you've probably already gathered from the previous post, I'm a big Project Euler fan. I joined the discord community in April 2021, and quickly got involved in helping it grow. In January 2022, I built a bot to track every member's progress, announcing each of their solves in a dedicated channel. Today the server has ~2500 people, including some very talented members who are always great to talk to, and I'm its main administrator.

This bot is probably one of the biggest projects of my life, since I've been actively maintaining it for 4 years, and it now has a huge number of features.

To give you an idea, this project involves:
- About 7000 lines of code
- A bit over 2,000,000 requests made to fetch data.
- Many different technologies: async, Pillow, Selenium, SQLite3, ...
- A great way for me to learn how to run long-lived projects on remote servers.

Here's a quick diagram of the technologies used: (as a reminder, the code is available at https://github.com/pacomef/ProjectEulerBot)

![Diagram of the technologies used by the bot]({{ "/_images/pe-bot/workflow.png" | relative_url }})
{: .img-wrap}

Here's an example of a graph the bot can generate with a simple command (this one shows the number of problems I've solved over the last 6 years):

![Project Euler progress statistics]({{ "/_images/pe-bot/statistics-pacome.png" | relative_url }})
{: .img-narrow}

Or this kind of animation, showing a user's progress live, as problems get published over time:

![Project Euler progress statistics, gif version]({{ "/_images/pe-bot/pacome_f.gif" | relative_url }})
{: .img-narrow}
