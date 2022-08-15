---
title: "The God's number"
date: 2016-11-20T05:29:25+05:30
categories: ["Mathematics"]
ShowToc: true
---

## Why is it the God's number?

According to me, a human cannot figure out the minimum number of moves to solve a scrambled cube just by looking at it, since it is difficult to imagine what will
be its state when a move is made, though it may be possible (by extraordinary beings or if the cube is in just about solved state).

## Alright, but how is the God's number 20?

There is a bit of(may be more) math involved in it, so bear with me.
There are 43,252,003,274,489,856,000 possible permutations of a rubiks cube, refer this link to see how it is derived https://en.wikipedia.org/wiki/Rubik's_Cube#Permutations.

We can use this number to derive the god's number.

Consider any scrambled state of a rubik's cube. Since there are 6 faces of the cube, each face can be rotated in two ways i.e., clockwise or anti-clockwise. That gives us 12 possible states of the cube (imagine scrambled state as a node from which 12 other nodes emerge) after a move. We can land into any one of these states if we execute one move.

Now, when we land into a state and execute another move, there are 11 possible states emerging from it, not considering the 1st state (we do not want to go back right).

This means that there are 11 such possible states for each of the 12 states. 11 other states emerge from the 11 previous states and so on. If we do N number of moves then according to our graph plotted(in our head) there will be

`12+(11*11*11*11*...n-1 times) = 12+11^(n-1).`

But we know that there are only 43,252,003,274,489,856,000 possible states, we can say

`12+11^(n-1)<=43,252,003,2749,489,856,000=4.3*10^19.`

Do some math and you get n<=20.

This is the optimal number of moves to solve the cube. Well we do not solve it in 20 moves because any of the move we do, we land into the non optimal region of set of moves to solve the cube, we round about throughout the graph and come back to the solved state if we know to solve the cube.
