---
title: Divine Journey
tag: project
order: 7
summary: An adventure on modded Minecraft, requiring automation of every kind.
link_label: details
link_url: "#"
lang: en
permalink: /en/projects/divine-journey/
translation_url: /projects/divine-journey/
photos:
  - "/_images/dj2/quest_alchemistry.png"
  - "/_images/dj2/craft_philosopher.png"
  - "/_images/dj2/integrated_dynamics.png"
---

<div class="summary-box" markdown="1">
Quick summary:
- I spent an enormous number of hours completing a Minecraft-based game that demands real, continuous thinking and full automation.
- The quantities of items needed to complete the game are massive, and it's mainly a logistics challenge.
- Most people who try the game give up after getting stuck due to a lack of automation.
</div>

Divine Journey is an "expert modpack" for Minecraft. The idea is to heavily modify Minecraft by adding hundreds of machines, materials, chemical compounds, sorcery, electricity, planets, and enemies. Each "mod" can live independently of the others, but a modpack makes them interact, blending the way certain items get crafted.

Divine Journey 2 is a "linear" modpack, built around quests (1600+), split into 30 chapters, and each chapter must be mostly completed before moving on to the next. So there are ages of civilization that you can reach, one after another.

Example of a quest tree for the chapter focused on chemical processes:

![Quest tree for the alchemy chapter]({{ "/_images/dj2/quest_alchemistry.png" | relative_url }})
{: .img-wrap}

Each quest roughly corresponds to obtaining one item, which is built using the previous items. And in each chapter, you typically need to use the final item of the previous chapter about twice, to make the final item of the current chapter (going through countless machines!). That works out to about 2**29 = half a billion items needed to reach the last chapter, which then doesn't care anymore and multiplies every required quantity by nearly a thousand.

Here's an item crafted toward the last chapters, which consumes dozens of others, for example:

![End-game craft consuming dozens of items]({{ "/_images/dj2/craft_philosopher.png" | relative_url }})
{: .img-wrap}

So, above all, it's a huge logistics challenge — you need to be able to:
- Generate energy, and deliver it to the machines that need it, knowing that not all machines receive the same type of energy
- Move all items from one machine to another, so that the machine can run automatically, and above all: 24/7, even when the player isn't there to fix problems, as long as the server is running
- Store all items, and have a system to get another item on demand, since not every item is worth automating continuously (which literally requires automating every step from raw materials to the final item, imagine doing that for just a motherboard!).
- Speed up every process more and more, to keep up with a demand that only grows from chapter to chapter!
- Make sure raw materials hold up, and aren't consumed faster than they're gathered.

On top of these problems comes lag, i.e. the load on the server's CPU, because even though having 15,000,000 of an item A can be reduced to a simple integer, having to use that item 15,000,000 times across different machines is quite different. The number of machines needed is what makes the whole task so heavy, because the machines keep track in memory of which items they contain, what percentage of the current task has been completed, and above all they interact with nearby machines, which adds listeners everywhere.

Here's an example of significant lag I often had to deal with: a thousand items on the ground. All the text shows the time consumed by each item, on the CPU, during a "tick," Minecraft's time unit, equal to 0.05 seconds when the server has no trouble keeping up. All these items ended up on the ground because, 2000 meters away, a machine got stuck, since one of the items it needed wasn't being produced fast enough anymore, due to a lack of resources. Then, the other item being fed into it stopped being consumed, and its storage got saturated. That caused a chain reaction, impacting all the storages upstream, and after 2 hours, all those items ended up on the ground, where they generate far more lag than they would in the storage they were meant for, since it was full.

![A thousand items on the ground generating server lag]({{ "/_images/dj2/lag.png" | relative_url }})
{: .img-wrap}

Having an enormous amount of cable is also very heavy on the server, since a cable is allowed to carry several types of items, which then need to know which machine to head toward, based on the filters set.

What I still find amazing, despite all this, is the logistical freedom this kind of modpack gives you. Minecraft is already Turing-complete without adding anything to it, and you can build computers simulating Tetris in it, for example. But by adding mods that focus heavily on industrialization and programming, you very quickly get access to very literal programming languages.

Most of this is made possible by Integrated Dynamics, which lets you measure, manipulate, and code pretty much anything you can think of. Integrated Dynamics networks have as many instructions as listed here: https://integrateddynamics.rubensworks.net/book/manual/logic_programming.html.

![Integrated Dynamics network reading plant attributes]({{ "/_images/dj2/integrated_dynamics.png" | relative_url }})
{: .img-wrap}

You can find bitshifts, functors, ways to measure the server's CPU performance, the exact time since the last rain (in milliseconds), and much more. It's a freedom that allows for infinitely complex systems. In the photo just above, the blue cables are from Integrated Dynamics, and they're used to read the attributes of plants growing in the middle of the small setup, to check whether the game assigns them a specific piece of metadata, and to harvest the plants if that attribute appears, in order to retrieve a specific item. All of this at a phenomenal speed (but capped so as not to add too much lag).

All of this took me around 700 hours to finish the game from start to finish. From what I understand, a lot of people finish it in a bit under 1000 hours, so I think I'm right around average. Many people simply don't finish it because they haven't automated their system enough, which pushes them to extremes for quests that are otherwise much simpler with automation.
