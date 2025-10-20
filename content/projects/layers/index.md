+++
date = '2021-08-31T00:00:00-00:00'
draft = false
title = 'Layers'
tags = ['Roblox', 'Plugin']
showTags = true
hidePagination = true
+++

A photoshop-like layering plugin for manipulating and visualizing sections of Roblox builds.

<div style="line-height:50%;">
    <br>
</div>
{{<imagerow left="/images/Devforum.png" link_left="https://devforum.roblox.com/t/layers-photoshop-like-layering-tool-for-roblox-builds/1400744" right="/images/Creator_Store.png" link_right="https://create.roblox.com/store/asset/7203627668/Layers" gap="15px" >}}

<!--more-->

<br>
	{{< youtube YKVubBuyVrU  >}}
</br>

In building or modeling, I often want to focus on specific parts/aspects of a build, and it can be difficult to do so when other world geometry gets in the way. The ability to break a build into individual layers is helpful here because each "stage" of development becomes its own quasi-immutable thing that you can refer back to. It's also incidentally helpful with respect to organization, managing scope, and with managing things like volumes, which you might want to be visible while working in Studio, but not in a live game.

### Pitfalls
_Layers_ was designed to solve this problem. Unfortunately, due to engine limitations, the plugin was implemented in an unintuitive way. It is difficult to link any kind of plugin state with the world model without doing something obtrusive. _Layers_ relied on Collection Service to keep track of which instances were in which layers, and over time this began to feel like a lot of bloat. There is also not currently a great way to mark an instance as "non-renderable," so the plugin moved instances in and out of Server Storage instead, which came with its own complications. The alternative would have involved controlling the local transparency modifier for applicable instances, but this also lead to problems with selection (solveable with more hacky behavior, which really isn't ideal when it starts piling up).

Other issues were related to UX. It’s difficult to adjust to a layers-based mental model. Ideally, you shouldn’t have to. Working in a 3D environment is not directly analogous to a 2D environment like photoshop. It’s hard to tell what instances are in what layers. Therefore, moving instances between layers is confusing. It’s also hard to turn the plugin “off” or to work around it, e.g. where do instances go that were created whilst the plugin was inactive or before it was installed? How should it behave in team create? How do we handle layer conflicts in general? &c.

### Conclusion
I'd like to revisit this someday, though there are alternatives now. I think a simplified version would work well for things like volumes, but I also think there is potential for an approach that isn't as coupled to the typical 2D solution.