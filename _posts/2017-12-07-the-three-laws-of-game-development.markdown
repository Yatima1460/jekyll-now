---
layout: post
title: The Three Laws of game development
date: 2017-12-07 04:49:00 +0100
description: The main problems with game development and how to fix them
img: 11000903_electrified-creeper-2.jpg
tags: [Game Development]
---

I'm finishing my game to publish on Steam and I noticed something during these months of development: there isn't a real book about design patterns to follow for game development or good guidelines in general, well it's true that there is the famous Design Patterns by The Gang of Four but it's too generic and not really applicable to the specific gamedev world; I don't want to write a book in this blog post obviously but at least I want to summarize the biggest problems I had during the development and what are the best strategies to fix them.

**1.Value-Quality Law**

I still believe to this day that the first law of game development should be the Value-Quality law or as Carmack said:

![Carmack at GDC 2004]({{site.baseurl}}/assets/img/carmack-gdc2004.PNG)

>[...] You can do quality and you can do value and if you want to be a successful company you wanna focus on value, because you can do something that may be extremely artistic, may be the work you know of a master-craftsman and is extremely high quality, but if it's not providing value to the people that are actually gonna buy the game, it's not the best thing to be working on, and there is certainly a place for art, as there is in any media but I don't think it's correct to look for, or expect, or even try to make something that's expected to be a mainstream AAA title a work of art; [...] I think it's kind of following the wrong path there.<br><br>
_[Carmack on Gaming Art, Value and Quality - GDC 2004](https://www.youtube.com/watch?v=Ec3U16FhjNc)_

Pretty self-explanatory, to summarize what Carmack said you don't need to add 8K textures, a work of the art AI and 100K polygons trees to your game if the players will not care, it's wasted time and money.

(That is probably the reason why the GOAP AI disappeared, but that's a story for another article)


**2.Survivorship Bias Law**

![Slenderman]({{site.baseurl}}/assets/img/slenderman.jpg)

Here it gets a little tricky, the Survivorship Bias phenomenon is what happens when you try to draw some conclusions from some data but you are actually overlooking other data that didn't make it past a selection process;

let's make a simple example here:



Let's say you are developing the next cool horror indie game and before publishing it you want to check the top selling horror indie games on Steam and you make a list of what are the features the players hate the most, after scrolling all the comments of the top 10 horror indie games you find out that the most hated thing is the fact that you can't jump; so you start thinking: "eheh I will add jumping mechanics to my game so it will perform even better than the top selling horror indie games on Steam" (obviously after you are on par on every other feature); then after adding the jump mechanic you publish your game and you notice it's performing poorly, why is this happening?



You fell into the trap of the Survivorship Bias phenomenon, you just drew conclusions by using only the Top 10 Selling Horror Indie Games on Steam, you aren't seeing the _whole picture_.

Let me explain:

The Top 10 Games are the Top 10 _even without_ having the jump mechanics!

So now there are two possibilities:

- The jump mechanics is actually present in the vast majority of all the other games not in the Top 10.

- The jump mechanics is almost not present at all in any indie horror game on Steam.

Conclusions of possibility #1:

This means that the bad games are unconsciously considered bad by the players _because they actually have the jump mechanics_ (maybe it ruins the horror feel?) or/and the fact that the jump mechanics isn't in the Top 10 means that _having or not having a jump mechanics doesn't influence the score your game will get on Steam_

Conclusions of possibility #2:

Congratulations, you just found a feature that everyone wants and isn't present in any game of the genre you are analyzing, maybe adding it will actually make your game the #1 selling one on Steam, but you can draw this conclusion only after analyzing the bad games too and find out that the jump mechanics isn't present there too, and you need to analyze _all_ the indie horror games on Steam.

See the problem of the Survivorship Bias now?

Obviously the Survivorship Bias happens because you are breaking the first law:

adding a feature that even the Top 10 selling games don't have doesn't provide value, but only quality!

Further Reading: [Survivorship Bias (Wikipedia)](https://en.wikipedia.org/wiki/Survivorship_bias)

**3.Feature Creeping Law**

![Electrified Creeper]({{site.baseurl}}/assets/img/electrified-creeper.png)

_The electrified creeper is actually a good example of feature creeping_

You start programming your enemies, you want that when an enemy is hit with a big weapon the enemy will turn into ragdoll mode and will fly away, 

*then you notice something:*
too many ragdolls are CPU intensive, so you make them disappear after a while;

*then you notice something: *
making them vanish when the player is watching is a very ugly effect, so you think about the idea of slowly sinking them in the terrain as a cool effect, but 

*then you notice something:*
some ragdolls could fly away on top of carriages or roofs "does it really make sense that they sink into the wood?", so you start developing an algorithm to make them disappear when the player isn't watching;

*then you notice something: *
what if the player stares at a big mountain of corpses? 
They will not disappear and the game will lag! 
Should I add a hardcoded disappearance time?

...and you get lost in the rabbit hole of feature creeping.

(Fun fact: this actually happened to me)

The Feature Creeping phenomenon is when you start to add extra features that go beyond the basic functionalities of your product and then it will just become bloatware.





The first reason why feature creeping happens is simply because you broke the Value-Quality law, almost zero players will care that enemies will disappear in front of their eyes, they know ragdolls are performance heavy and enemies disappearing in front of your own eyes always happened during the past 20 years of videogames history;

Developing a game without ragdolls disappearing? Cool.

Developing a game in half the time with ragdolls disappearing? Even better.

Always develop your game *horizontally* not *vertically*, in every iteration/new version try to add a bit of every feature instead of just focusing on a single feature for an entire week.

No one will care that deeply about that work of art feature, but all the players will care about having a lot of several features working nicely together.



The second reason is probably because you broke the Survivorship Bias law, you just added a feature you thought it was cool because the top selling games don't have it, but they are the top selling probably because they didn't add it and focused on other things!

**Post-Mortem about World of Warcraft:**

![WoW Fishing]({{site.baseurl}}/assets/img/wow-fishing.jpg)

This is the main reason why I consider World of Warcraft (obviously vanilla) one of the best well designed MMORPGS ever, it's the most *horizontal* MMORPG ever, the developers didn't focus on the quality of a single feature, but on the *quantity*; you can do everything in that videogame: from selling herbs you found in a swamp, to fishing in a pond with a random guy you met, to killing an elder god, or just jump on a fountain while wearing a Santa hat! If you add a lot of different features you can attract all the types of players and **create immersion**, but if you do only very few features, you will only target a minority)

Further Reading: [Feature creep (Wikipedia)](https://en.wikipedia.org/wiki/Feature_creep)

**Conclusions:**

Are you developing a game?

First try the concept by just using cubes without texture and sound: is it funny?

If the answer is yes start to drink a cup of coffee and develop it on your mechanical keyboard while keeping in mind the *The Three Laws Of Game Development*

*Cubes!?!?! *
*You don't believe me, don't you?*

![Overwatch cubes]({{site.baseurl}}/assets/img/overwatch-cubes.PNG)

*The image above is Overwatch during development, a bunch of cubes and a Doge as the payload icon.*
