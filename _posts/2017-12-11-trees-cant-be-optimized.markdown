---
layout: post
title: Trees can't be optimized (TODO)
date: 2017-12-11 05:33:00 +0100
description: Your enemy if you like nature
img: tree_wireframe1.jpg
tags: [Game Development, Graphics, Performance]
---

In this blog post I want to discuss about a problem that probably the average programmer doesn't know: trees are evil in game development.

Let's get straight to the point: there isn't a good way to make trees in videogames, and for "good" I don't mean beautiful, but optimized.

Trees are always performance heavy no matter what.

Why trees are always performance heavy?
First you need to know how trees can be made, there are two ways in videogames:

**Polygon trees**



Polygon trees are probably how are you imagining them, every single detail is made of triangles, but in reality you will probably never find them even in AAA videogames, they are too performance heavy, a single well detailed triangles tree will have around _ triangles, it's just too much for your GPU.
Maybe few Polygons trees? That's okay but you will never be able to build a forest with them.
To make a comparison remember that in general nowadays (2017) the hard limit for hardware is about 1 million triangles,
as an example a game with the most detailed character ever is in Ryse where the roman soldier has around 150K polygons, consuming about a bit less than 10% of the available triangles.

**Opacity Masked trees**


Opacity masked trees use a trick solve the problem of polygon trees by using quads as leaves and rendering them flat with opacity.


*The actual opacity masked tree*


*The leaves transparency texture*


*The final result*



The upside is that you have very few polygons so you can actually place a lot of them, the downside is the curse known as **pixel overdraw**.


**The pixel overdraw phenomenon**



Every pixel on your monitor isn't always rendered once per frame, some pixels may be rendered two or even more times, think about it: you have a videogame with a glass window and a banana behind it, first the GPU needs to render the banana pixel and then the window glass pixel!
The pixel overdraw phenomenon is what happens when a pixel needs to be rendered more than once; sometimes it's necessary to make glass in videogames or transparent objects but it can become a curse for a simple reason: *the GPU can render only a limited number of pixels every frame*, this limit is known as **fill rate**.
This means that if you are in front of glass window and it's filling the entire screen the GPU is actually working as if connected to a monitor with double the pixels! 

Instead of drawing 1920\*1080=2073600 pixels, it's actually drawing 1920\*1080\*2=4147200 pixels!
(as you can imagine if you have two transparent objects filling the entire screen the GPU is actually drawing three times the number of pixels)

*Yes, but what this have to do with trees?*

Remember that we are using transparency for leaves to have less polygons?

Exactly!

If you make a forest full of Opacity Masked trees what will happen is that all the transparent pixels will align and it would be the same as having a monitor with double the pixels connected or even more!


*Screenshot of the phenomenon in Unreal Engine*
*White = a lot of overdraw*


Now I have explained why both the polygons trees and the opacity masked trees are bad: polygons trees have just too many polygons for the GPU to make a forest and the opacity masked trees are still bad to make a forest because the transparent pixels will align and will be rendered even 10 times or more.

There isn't a good way to make trees in videogames.
You need to choose the best type of tree by analysing the current scene
Do you have polygons to spare? Then use polygon trees
Do you have fill rate to spare? Then use opacity masked trees.

**A "solution"**

The advice is to make something *in between* polygon trees and opacity masked trees I like to call them Polygon Opacity Masked trees, a tree like the image below, where the polygons somewhat follow the leaves but transparency is still applied, they generally work well everywhere without the need to squeeze performance.

**Conclusions**

Generally using Opacity Masked trees is a better choice, the polygons hard limit is very low, as we said about 1 million when a very detailed character will use 10% of this pool; but the fill rate nowadays is very high: a NVIDIA 980Ti can render about 85 billion pixels/second, this means about 1 billion pixels/frame to achieve 60FPS, it's true that it seems very high but consider that a lot of pixels in a scene are rendered even when not seen and in an average videogame you will hit the 1 billion limit when watching an entire forest from a top of a mountain.

So if you are doing a realistic graphics videogame my advice is to just use Opacity Masked trees everywhere and if you are noticing a performance problem switch to the Polygon Opacity Masked trees, you should use Polygon Trees only for single trees are not for forests.

If you are doing a low poly videogame use Polygon Trees obviously.

And remember, trees are evil!



