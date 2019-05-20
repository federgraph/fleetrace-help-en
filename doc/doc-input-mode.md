---
layout: default
lang: en
title: Input Mode
---

# Input Mode

## Overview

The input mode is related to direct,
manual input of finish positions into the Race columns of the grid on page Event.
Input mode can be either Strict or Relaxed.

It is always the goal to maintain consistency of input data.
Identical numbers or gaps in the list of finish positions must be eliminated as soon as possible.
Strict mode is used to automatically maintain the rules.

In relaxed input mode the program reacts relaxed upon your input.
It does not bother you with automatic adjustments.
Anyway, we do recommend strict mode,
because in this case it is the user of the program who can relax.

Input of finish positions is the job of the timing provider.
The results of the race will be transferred when the race has finished
from the race part of the program to the event part of the program.
This is why few corrections should be input directly into the Event-Grid.

## Strict Mode

Using strict input mode it is guaranteed that running numbers of finish positions are maintained from one upwards.

Should a number have been used already, a gap is created and all following numbers are counted up by one.
This is the expected behavior.
It enables easy manipulation of finish positions,
without the need to maintain the whole list manually.

Should a newly input number create a gap at the end of the list,
the input value is corrected automatically.
This behavior is not always expected, but it makes sense.
You can take advantage of it when entering finish positions in real time.
If you do not know the current position, just input a high enough number,
the Bib will be placed with the correct running number at the end of the list.

The event can be switched from relaxed input mode to strict input mode only when the conditions are fully met.

## Relaxed Mode

Sometimes, finish positions need to be stored exactly as input.
This is the case if you copy an existing result list line by line.
Just let me mention here that this does not count as good practice.
If you make a mistake somewhere,
it can be expensive to reach consistency at the end of the input process.
While the program is able to support the search for errors by color-marking inconsistencies,
it is much better to reach strict input mode early,
and make all other corrections with the help of strict input mode.

However, there is one important use of relaxed mode - when the program reads a text or xml file.
If no invalid manipulation was done to the editable data file,
the program will be able to switch to strict input mode at the end of the reading process.

You can at any time switch back to relaxed input mode without condition.

## Conclusion

Strict input mode exists for ages, and so it is not mentioned often today.
It enables a quick what-if-analysis within the [desktop application](../applications/FR93.html)
and also within the new [Silverlight Client](../silverlight/FRIA05.html).
