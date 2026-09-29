+++
date = '2026-04-01T00:00:00-00:00'
draft = false
title = 'Infinite Tennis'
tags = ['Roblox', 'ECS', 'Jecs', 'React']
showTags = true
hidePagination = true
+++

A fast-paced, arcade-like tennis game.

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

Infinite Tennis is a work-in-progress, semi-competitive, arcade-like tennis game. The gameplay is fast-paced -- the average period between returns is less than a second. The trajectory of the ball is influenced by a number of factors, including the ball's incoming angle, the player's position on the court, the shot type, swing direction, and the directional bias/aiming bar, all of which together make the gameplay fairly deep and strategic.

Because the game is semi-competitive, I took a custom server-authoritative approach to simulating the ball. Specifically, in implementing a simple, deterministic physics pipeline for the ball, I get a single, reliable source of truth for its position. The server owns the ball, and the server and clients all independently predict its motion, the latter based on reliable updates communicated by the server. This has allowed for me to explicitly handle the extrapolation logic for high-latency players, and it makes sanity checking player inputs much simpler.

Players can play real opponents or simulated agents. By default, matches end after two sets. Though the gameplay can be competitive, the environment is designed to be casual and relaxing. It's thematically inspired in some ways by the book _Infinite Jest_ (not super explicitly, but in a vibes kind of way), and working on the environment and atmosphere has been surprisingly rewarding.

The game supports keyboard and mouse, touch, and gamepad controls. I hope to release it sometime toward the end of 2026.