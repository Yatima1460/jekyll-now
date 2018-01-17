---
layout: post
title: How to build a quantum computer in D&D (DRAFT)
---

**Warning Note**

I will try to explain quantum computers in the simplest way possible.
Everything explained here is in layman's terms, nothing is advanced math or physics and you don't even need to understand programming.

**Prerequisites**

It's better if you know at least logic gates.

**The bit**

![Bit]({{site.baseurl}}/images/bit.png)

Every classical computer uses a binary system to encode information, 0 and 1.
During the beginning of 1900 there were prototypes working in ternary: 0,1 and 2 but as you can imagine they failed instantly;
there aren't real advantages and you need complex circuitry.
Binary systems became pretty widespread simply because it's easy to create them: vacuum tubes, transistors and so on; just turn the voltage on or off and you have a binary system.

**The quantum computer**

A quantum computer is just a computer that uses qubits instead of bits to encode information.

**The qubit**

So what is the qubit?
Well to put it simply a qubit is just a 3D bit.

A bit is 0 or 1, a point, a 0-dimensional bit.
A 1D bit is a point on a segment between 0 and 1
A 2D bit is a point on a circle
A 3D bit is a point a sphere!

The north pole is 0.
The south pole is 1.
All the other points are just values "in between".

Yes you can encode information as a point on a sphere!

**Hardware**

What do we use to build qubits (points on spheres)? 
The spin of elementary particles like electrons.
If you don't know what is a spin just imagine it as the north pole of its rotation. 
So quantum computers just use rows of single electrons encased in very small cages to encode information.

**Interesting quantum effects**

Obviously quantum computers don't just use electrons to encode a point on a sphere, but they exploit some interesting behaviors
elementary particles exhibit:

- "Collapse of the wave function": it just means that when you try to convert the 3D bit (qubit) into the classical bit the probability
of becoming 0 or 1 is proportional to how much the point is near the north pole (0) or south pole (1); if the point is at the equator it has 50% chance of becoming 0 and 50% chance of becoming 1.
- Entanglement: quantum entanglement just means when you have set up two qubits in a way that they are pointing at opposite directions but that's the only thing you actually know; you don't know where the points on the spheres are, just that they are opposite; and when you collapse one the other will collapse instantly *no matter the distance* to the opposite value.
Einstein called this "spooky action at a distance".

**Quantum gates**



