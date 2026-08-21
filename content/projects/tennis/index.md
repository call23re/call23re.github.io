+++
date = '2026-06-01T00:00:00-00:00'
draft = false
title = 'Tennis'
tags = ['Roblox', 'ECS', 'Jecs', 'React']
showTags = true
hidePagination = true
+++

A work-in-progress, fast-paced tennis game.

<br>
	{{< youtube D2bt8n83aig >}}
</br>

<div style="line-height:50%;">
    <br>
</div>
<a href="https://www.roblox.com/games/87097450654989/tennis">
	<img src="/images/Roblox.png">
</a>

<!--more-->

Infinite Tennis is a project I work on intermittently (when I have the time). The gameplay is fast and the mechanics are fairly deep. The trajectory of the ball is influenced by multiple factors, including the ball's incoming angle, the player's position on the court, the shot type, swing direction, and the directional bias bar. The game follows a simple, custom server-authoratative networking model, meaning the ball itself is simulated locally via a comparably simple, custom physics pipeline. This helps to avoid a number of issues relating to cheating and network ownership.

Players can play real players or simulated agents. By default, matches end after two sets, but later I intend to implement custom matches for shorter sessions. I also intend to implement ELO and leveling systems for progression.

The game supports PC, mobile, and console controls. I hope to release it sometime toward the end of 2026. It's thematically inspired by the book _Infinite Jest_.