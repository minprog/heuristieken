![](chipsandcircuits2.jpg)

## Introduction

Chips (or more precisely: ''integrated circuits'') are found in your PC, MacBook, Android Phone and microwave oven where they perform a diversity of functions, ranging from timekeeping and motor control to arithmetic and logic. Basically a small plate of silicon, chips are usually designed logically and subsequentially transformed to a list of connectable gates. This list, commonly known as a ''net list'' is finally transformed into a 2-dimensional design on a silicon base.


This last step however, the physical real-world process of connecting the gates, is highly volatile. Good arrangements with short nets lead to faster circuits, whereas poor arrangements with long nets lead to slower circuits. Besides, shorter nets are cheaper than long nets, so there is no doubt that a good arrangement of logical gates and short nets between them is of vital importance, both economically and performancewise.


To make things easier, we will consider the wiring problem only. The gates have already been arranged, and all it takes is finding very short wiring patterns.


## Example
![](netlist1.gif) Netlist #1
![](Cc1_subopt.gif) A suboptimal wiring for netlist #1.
![](Cc1_optim.gif) An optimal wiring for netlist #1.

This is an integrated circuit built up from five gates that need to be connected. The connections ("nets") follow the grid in a Manhattan style. Luckily enough, the wires don't cross. Sometimes they have to and when they do, the base consists of multiple grid layers. Besides going North, South, East and West, nets can also go Up and Down, and the distance between levels is identical to the distance between grid points.


## Assignment

![](print1.gif)
![](print2.gif)

Print #1 and Print #2 are arrangements of gates on a base, and all it takes is to wire the appropriate gates together. There are three net lists (in [txt-format](http://heuristieken.nl/resources/CC_netlists2.txt)) for each print. Each net list needs to be implemented. Nets can only follow the grid, only one wire per segment, and one step costs 1 unit length. Nets that are aligned among the same grid line are said to be in _collision_. If there is one collision in one arrangement, the circuit cannot be used. Nets can also go up and down to lower and higher layers, also at the cost of 1 per level. The assignment is to implement all nets in all netlists at minimum cost.


A few steps to pave the way towards a program:


1) Build a computer program that holds a data structure for a grid with fixed gates. 


2) Expand your program by making a data structure for a net list. Make sure it holds a few nets, and that the program has a cost function to calculate the total wire length.


3) Add 7 more layers. Try to get all the nets in. You can either build up wire-by-wire, or remove collisions one by one. 


4) Try to get all the nets in with minimal costs. Record all your results, so you can present them later.


## Advanced

* Randomly generate some new net lists. They should be of equal length to the original net lists. Which are solvable, which aren't? Which have good solutions, which haven't?

* For each of the three arrangements, try to determine the relation between the number of wires and the required number of layers.


==Questions & Answers ==

**1) "only one wire per segment", does this means multiple nets can use a grid intersection?**

No, it doesnt. Each grid intersection can support just one net (or "wire"). Still, this might cause problems around the logical gates, so maybe an exception should be made there. We don't know yet, as this is quite a new case.


**2) The edges of the prints as shown in the pictures, can we use them to route nets, or should the nets stay clear of the edges?**

Yes. You can consider the base to extend a little beyond the picture, and therefore all intersections in the picture can be used.


**3) A new layer, should it be somewhere specific, or can we place it where we want?** 

A new (second, third, fourth) layer provides a means for your nets to go down one extra level. A new layer is of equal dimensions as the original base. But, if a layer (for instance a seventh or eight layer) is unused, it should not be placed of course, to keep manufacturing costs down.


**4) Can unconnected gates be removed?**

We have updated the net lists and gate configurations. No unconnected gates exist anymore.


**5) Can nets run through gates?**

No! Every net touches exactly two gates, one at both ends. 


**6) Can loose segments of several logical gates be distributed elsewhere on the base?** 

We don't expect this situation to be present, but the answer in any case is no; gate locations are fixed.
