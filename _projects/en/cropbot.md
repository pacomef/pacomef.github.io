---
title: Cropbot
tag: project
order: 9
summary: A Twitter bot that automatically crops and posts images.
link_label: details
link_url: "#"
lang: en
permalink: /en/projects/cropbot/
translation_url: /projects/cropbot/
photos:
  - "/_images/cropbot/cropthisbanner.png"
  - "/_images/cropbot/presentation.png"
  - "/_images/cropbot/twitterlogo.png"
---

<div class="summary-box" markdown="1">
Quick summary:
- I built a Twitter bot, my first project needing a 24/7 deployed service, whose goal was to crop people's images on Twitter whenever a clearly uniform part of the image was just due to a poorly taken screenshot.

Repo: [github.com/pacomef/twitter-cropbot](https://github.com/pacomef/twitter-cropbot)
</div>

This is a project I built in 2020, and I'm including it here because it's probably one of my very first projects, and I'm still fond of it, even if it isn't anything grand.

The idea was to have a bot running 24/7 on Twitter (I stopped the bot well before Elon Musk bought Twitter and renamed it X), whose main job was to neatly crop people's photos.

An example is worth a thousand words, so here's the tweet pinned at the top of the bot's (still existing) page:

<div class="tweet-embed">
<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Quick reminder on how to use me! DM me for further advice <a href="https://t.co/Z6uXl9ynH5">pic.twitter.com/Z6uXl9ynH5</a></p>&mdash; Crop This - Bot (@CropThisBot) <a href="https://x.com/CropThisBot/status/1302980856957546496?ref_src=twsrc%5Etfw">September 7, 2020</a></blockquote>
</div>

<script async src="https://platform.x.com/widgets.js" charset="utf-8"></script>

The idea was to trace four lines starting from the 4 sides of the image, and detect the largest distance that could be covered without the pixels changing by more than a given delta.

The bot was probably used a hundred times or so, all in all. (Sometimes for questionable images, so maybe don't venture too far if you start digging into the bot's "exploits".)

To run the service, I used Heroku, which was a free way to run a server around the clock, with the ability to go to sleep and stop consuming credits as soon as the main script wasn't running anymore. That made it perfect for a simple Twitter listener, waiting for someone to mention the bot, then fetching the photo and editing it using Pillow.
