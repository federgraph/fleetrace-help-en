---
layout: default
lang: en
title: Event Properties
---
		
# How to setup Event Properties

The Event Properties (EP) for an sailing competition event (Event) with 20 Booten, 
10 normal race and one medal race can be setup like so:

```
#Params

DP.StartlistCount = 20
DP.ITCount = 0
DP.RaceCount = 11

#Event Properties

EP.Name = L 2012 470 W
EP.ScoringSystem = Low Point System
EP.Throwouts = 1
EP.ReorderRAF = False
EP.DivisionName = *
EP.InputMode = Strict
EP.RaceLayout = Finish
EP.NameSchema = NX
EP.FieldMap = N3
EP.FieldCaptions = H,C,NOC
EP.FieldCount = 3
EP.NameFieldCount = 3
EP.NameFieldOrder = 123
EP.UseFleets = True
EP.TargetFleetSize = 20
EP.FirstFinalRace = 11
EP.IsTimed = False
EP.UseCompactFormat = True
```

- StartlistCount must be set to 20, because the Event has 20 participants (Entries). 
- TCount must be set to 0, because no times will be recorded, only finish positions. 
- RaceCount must be set to 11, because there are 10 normal races and one medal race. 
- Name is an arbitrary and short text and appears in Html format as heading. 
- ScoringSystem can remain unchanged. There may be an extra article. 
- Throwouts set to 1 means 1 race to throw out and can be changed from within the application. 
- ReorderRAF should be False and True only in special cases (depending on how the rules are to be interpreted). 
- DivisionName = * does not need change, this is always being used here. 
- InputMode should read Strict, if the information given is consistent (unique and/or contiguous), that should always be the case. 
- RaceLayout set to Finish is the correct Choice when you want to input data and see the finish positions instead of the points.
  This option can be changed from within the application. 
- NameSchema NX is the default and recommended for new files. 
- FieldMap set to N3 means that the name field N3 will be mapped to DisplayName column. 
- FieldCaptions contains the headings of the name columns. 
- FieldCount set to 3 means that 3 columns should be saved. 
- NameFieldCount set to 3 means that three columns should be shown in the Event Table (can be less). 
- NameFieldOrder 123 means that the three columns should appear in this order.
  No more than 9 columns will be shown. 
- UseFleets must be True, because there will be a medal race. 
- TargetFleetSize set to 20 corresponds to StartlistCount. Only in the medal race will we have smaller fleet (10). 
- FirstFinalRace set to 11 designates the medal race. The medal race is the last race, after qualification round, which in this case comprises 10 races. 
- IsTimed set to False means that no times will be stored. FR01 cannot store times. 
- UseCompactFormat set to True is the right setting most of the time, 
  because data in compact format is best for editing in external (spreadsheet) program. 

Starting from a good example you only have to adjust the following properties: **StartlistCount**, **TargetFleetSize** and **Name**. 
From StartList you delete surplus entries. 
FinishList can be deleted completely. 
FleetList and NameList will be explained in another Article. 
All the rest can be done from within the application, using the UI, the graphical user interface.

Here is the complete template for 470 W:

```
#Params

DP.StartlistCount = 20
DP.ITCount = 0
DP.RaceCount = 11

#Event Properties

EP.Name = L 2012 470 W
EP.ScoringSystem = Low Point System
EP.Throwouts = 1
EP.ReorderRAF = False
EP.DivisionName = *
EP.InputMode = Strict
EP.RaceLayout = Finish
EP.NameSchema = NX
EP.FieldMap = N3
EP.FieldCaptions = H,C,NOC
EP.FieldCount = 3
EP.NameFieldCount = 3
EP.NameFieldOrder = 123
EP.UseFleets = True
EP.TargetFleetSize = 20
EP.FirstFinalRace = 11
EP.IsTimed = False
EP.UseCompactFormat = True

NameList.Begin
SNR;N1;N2;N3
1003;Abc;Def;NOC
NameList.End

StartList.Begin
Pos;SNR;Bib
1;1000;1
2;1001;2
3;1002;3
4;1003;4
5;1004;5
6;1005;6
7;1006;7
8;1007;8
9;1008;9
10;1009;10
11;1010;11
12;1011;12
13;1012;13
14;1013;14
15;1014;15
16;1015;16
17;1016;17
18;1017;18
19;1018;19
20;1019;20
StartList.End

FleetList.Begin
SNR;Bib;R1;R2;R3;R4;R5;R6;R7;R8;R9;R10;R11
1000;1;1;1;1;1;1;1;1;1;1;1;0
1001;2;1;1;1;1;1;1;1;1;1;1;0
1002;3;1;1;1;1;1;1;1;1;1;1;0
1003;4;1;1;1;1;1;1;1;1;1;1;0
1004;5;1;1;1;1;1;1;1;1;1;1;0
1005;6;1;1;1;1;1;1;1;1;1;1;0
1006;7;1;1;1;1;1;1;1;1;1;1;0
1007;8;1;1;1;1;1;1;1;1;1;1;0
1008;9;1;1;1;1;1;1;1;1;1;1;0
1009;10;1;1;1;1;1;1;1;1;1;1;0
1010;11;1;1;1;1;1;1;1;1;1;1;1
1011;12;1;1;1;1;1;1;1;1;1;1;1
1012;13;1;1;1;1;1;1;1;1;1;1;1
1013;14;1;1;1;1;1;1;1;1;1;1;1
1014;15;1;1;1;1;1;1;1;1;1;1;1
1015;16;1;1;1;1;1;1;1;1;1;1;1
1016;17;1;1;1;1;1;1;1;1;1;1;1
1017;18;1;1;1;1;1;1;1;1;1;1;1
1018;19;1;1;1;1;1;1;1;1;1;1;1
1019;20;1;1;1;1;1;1;1;1;1;1;1
FleetList.End

#FinishList.Begin
#  The FinishList is empty, the event has not started yet
#FinishList.End

#W1

#Race 1 is enabled

#W2

#Race 2 is configured, but disabled
FR.*.W2.IsRacing=False

#W3

FR.*.W3.IsRacing=False

#W4

FR.*.W4.IsRacing=False

#W5

FR.*.W5.IsRacing=False

#W6

FR.*.W6.IsRacing=False

#W7

FR.*.W7.IsRacing=False

#W8

FR.*.W8.IsRacing=False

#W9

FR.*.W9.IsRacing=False

#W10

FR.*.W10.IsRacing=False

#W11

FR.*.W11.IsRacing=False

EP.IM = Strict
```

And of course, it is even easier if there is no medal race!

