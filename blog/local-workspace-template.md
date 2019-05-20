---
layout: default
lang: en
title: Workspace Template
---

# local workspace template

The L 2012 templates are now included in the fr01-local-workspace-sample download, 
using the following StartListCount values:

```
470 M (27)
470 W (20)
RSX M (38)
RSX W (28)
Laser M (48)
Laser W (39)
Finn (25)
Star (16)
49er (20)
```
<p>Here is a list of input tricks to remember:</p>

<li>Enable a race with Button X (Race sensitive = select a cell in a race column first)</li>
<li>Input a finish position into a cell with 99 Enter (99 = number greater than boats finished)</li>
<li>Delete finish position from cell with 0 Enter</li>
<li>Update finish position in cell with whole number Enter</li>
<li>Before the medal race, set the group value for all 10 participants to 0 with m Enter</li>
<li>Before the medal race, set the not racing flag for all other entries with x Enter</li>
<li>Delete the not racing flag from cell with -x Enter</li>
<li>Delete all penalties from cell with ok Enter</li>
<li>Input DSQ into cell with dsq Enter</li>
<li>Delete DSQ from cell with -dsq Enter</li>
<li>Specify RDG value for cell with rdg/points Enter</li>
<li>Set group value of cell to 0 with m Enter</li>
<li>Set group value of cell to 1 with y Enter</li>
<li>(Set group value of cell to 2 with b Enter)</li>
<li>(Set group value of cell to 3 with r Enter)</li>
<li>(Set group value of cell to 4 with g Enter)</li>

You can use page Timing to input the finish positions, but you don't have to. 
All input can be done via the grid on page Event. 
The events are in strict input mode; you input finish positions in order, starting from 1 and counting upwards. 
You don't have to enter the actual finish position, just enter a number bigger than the actual number. 
I use 22 for 470 W. 99 will always work in L 2012.
Correct a finish position by entering the actual number though.

If the actual number of entries or the actual number of races is smaller, 
then you can quickly update the template. It is sufficient to update parameters and properties. 
Additional data not used is deleted from the lists when you save the Event.

