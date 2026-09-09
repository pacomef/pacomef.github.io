---
title: Cropbot
tag: project
order: 9
summary: Un petit projet de début de lycée pour automatiser le rognage d'images sur Twitter.
link_label: details
link_url: "#"
lang: fr
translation_url: /en/projects/cropbot/
photos:
  - "/_images/cropbot/cropthisbanner.png"
  - "/_images/cropbot/presentation.png"
  - "/_images/cropbot/twitterlogo.png"
---

<div class="summary-box" markdown="1">
Résumé si pressé:
- J'ai réalisé un bot Twitter, qui était mon premier projet avec le besoin de déployer un service 24h/24, qui avait pour objectif de rogner les images de personnes sur Twitter, lorsqu'une partie claire de l'image était juste dû à une capture d'écran mal faite.

Repo: [github.com/pacomef/twitter-cropbot](https://github.com/pacomef/twitter-cropbot)
</div>

Ceci est un projet que j'ai réalisé en 2020, et je le met dans ce dossier car c'est sans doute l'un de mes tous premiers projets et je l'aime bien, même s'il n'est pas grandiose.

Le principe est d'avoir un bot disponible 24h/24 sur Twitter (j'ai arrêté le bot bien avant qu'Elon Musk ne rachète Twitter et le renomme X) dont le rôle principal serait de couper proprement les photos des gens.

Un exemple vaut mieux que mille mots, voici donc le tweet "accroché" en haut de la page (toujours existante) du bot :

<div class="tweet-embed">
<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Quick reminder on how to use me! DM me for further advice <a href="https://t.co/Z6uXl9ynH5">pic.twitter.com/Z6uXl9ynH5</a></p>&mdash; Crop This - Bot (@CropThisBot) <a href="https://x.com/CropThisBot/status/1302980856957546496?ref_src=twsrc%5Etfw">September 7, 2020</a></blockquote>
</div>

<script async src="https://platform.x.com/widgets.js" charset="utf-8"></script>

Le principe était de tracer quatre lignes, partant des 4 côtés de l'image, et de détecter la plus grande distance pouvant être parcouru sans que les pixels ne changent d'un certain delta donné. 

Le bot a du être utilisé en tout et pour tout une centaine de fois. (Des fois pour des images questionnables, donc ne vous aventurez peut être pas trop loin si vous commencez à explorer les "exploits" du bot.)

Pour faire fonctionner le service, je passais par Heroku, qui était un moyen gratuit de faire tourner un serveur h24, avec la capacité de se mettre en veille et d'arrêter de consommer des crédits dès que le script principal ne tourne plus. C'est donc parfait pour avoir un simple listener twitter, qui attend qu'une personne mentionne le bot, et récupère ensuite la photo et la modifie, à l'aide de Pillow. 
