---
layout: default
lang: en
title: Message Example
---

# Message example

## Overview

The data of application FR (event data) can be stored in xml format,
the compact text format or in native text format.
The individual formats can be converted in all directions without loss.
At the heart of the event data representation is a list of single line messages.

## Single line message

Single line messages are formed according to the Key=Value pattern.

The idea is like so (with indices in parenthesis):

```
FR.*.W[2].Bib[2].QU=DSQ
```

In reality the parentheses need to be dropped (this serves space and is easier to write):

```
FR.*.W2.Bib2.QU=DSQ
```

- To the left of the equal sign is the Key.
- FR designates the application type.
- The * in the second compartment stands for the anonymous division (this is good if messages are sent for one division only).
- W2 is the 2. Race.
- Bib2 designates the line in the table.
- QU means a penalty value (QUIT packet) is assigned.
- DSQ to the right of the equal sign is the Value.

## Protocol

Single line messages are formed according to the self defined protocol.
The program contains a robust parser for the protocol.

The Key (to the left of the equal sign) is composed hierarchically.
Individual levels/compartments are separated by a full stop.
The design of the protocol can be presented in a spreadsheet table.
Entries ending in X are indexed Tokens.
The leaf alias is an alternative name for the last token of the message key.

<table>
<tr>
<th>Level1</th>
<th>Level2</th>
<th>Level3</th>
<th>Level4</th>
<th>Level5</th>
<th>Level6</th>
<th>Leaf Alias</th>
</tr>
<tr>
<td>FR</td>
<td>Division</td>
<td>SNR(X)</td>
<td>FN</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>N1</td>
</tr>
<tr>
<td></td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>LN</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>N2</td>
</tr>
<tr>
<td></td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>SN</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>N3</td>
</tr>
<tr>
<td></td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>NC</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>N4</td>
</tr>
<tr>
<td></td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>GR</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>N5</td>
</tr>
<tr>
<td></td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>PB</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>N6</td>
</tr>
<tr>
<td></td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>N(X)</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
</tr>
<tr>
<td></td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
</tr>
<tr>
<td></td>
<td>&nbsp;</td>
<td>W(1)</td>
<td>STL</td>
<td>Pos(X)</td>
<td>Bib </td>
<td>&nbsp;</td>
</tr>
<tr>
<td></td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>SNR</td>
<td>&nbsp;</td>
</tr>
<tr>
<td></td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
</tr>
<tr>
<td></td>
<td>&nbsp;</td>
<td>W(X)</td>
<td>Bib(X) | Pos(X)</td>
<td>XX</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
</tr>
<tr>
<td></td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>QU</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
</tr>
<tr>
<td></td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>ST</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
</tr>
<tr>
<td></td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>FT</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
</tr>
<tr>
<td></td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>DG</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
</tr>
<tr>
<td></td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>Rank</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
</tr>
<tr>
<td></td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>RV</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
</tr>
<tr>
<td></td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
<td>IT(X)</td>
<td>&nbsp;</td>
<td>&nbsp;</td>
</tr>
</table>

STL initializes lines in table W or tables W(X).
SKK only uses one table.
There are other applications of the frameworks that use several tables.

As defined in level 4,
messages targeted for a line in W(X) can be assigned to the Bib (unique numeric key for a line in table W).

## Text format

The text format is in the main part a list of single line messages
that can be sent to the program as such one by one over the network or an internal connection.
Prepended in the text format are the parameters and properties for the event.

```
#Params

DP.StartlistCount=8
DP.ITCount=0
DP.RaceCount=2

#Properties

EP.Name=
EP.ScoringSystem=Low Point System
EP.Throwouts=0
EP.DivisionName=*
EP.InputMode=Strict
EP.RaceLayout=Finish
EP.NameSchema=
EP.FieldMap=SN
EP.FieldCaptions=
EP.FieldCount=6
EP.NameFieldCount=2
EP.NameFieldOrder=041256
EP.UseFleets=False
EP.TargetFleetSize=8
EP.FirstFinalRace=20
EP.IsTimed=False
EP.UseCompactFormat=True

#NameList

FR.*.SNR1000.N1=abc
FR.*.SNR1000.N2=def
FR.*.SNR1000.N3=ghi
FR.*.SNR1000.N4=jkl
FR.*.SNR1000.N5=mno
FR.*.SNR1000.N6=pqr

#StartList

FR.*.W1.STL.Pos1.SNR=1000
FR.*.W1.STL.Pos1.Bib=1
FR.*.W1.STL.Pos2.SNR=1001
FR.*.W1.STL.Pos2.Bib=2
FR.*.W1.STL.Pos3.SNR=1002
FR.*.W1.STL.Pos3.Bib=3
FR.*.W1.STL.Pos4.SNR=1003
FR.*.W1.STL.Pos4.Bib=4
FR.*.W1.STL.Pos5.SNR=1004
FR.*.W1.STL.Pos5.Bib=5
FR.*.W1.STL.Pos6.SNR=1005
FR.*.W1.STL.Pos6.Bib=6
FR.*.W1.STL.Pos7.SNR=1006
FR.*.W1.STL.Pos7.Bib=7
FR.*.W1.STL.Pos8.SNR=1007
FR.*.W1.STL.Pos8.Bib=8

#FinishList

FR.*.W1.Bib1.Rank=2
FR.*.W2.Bib1.Rank=3
FR.*.W1.Bib2.Rank=7
FR.*.W2.Bib2.Rank=4
FR.*.W1.Bib3.Rank=5
FR.*.W2.Bib3.Rank=8
FR.*.W1.Bib4.Rank=1
FR.*.W2.Bib4.Rank=7
FR.*.W1.Bib5.Rank=6
FR.*.W2.Bib5.Rank=5
FR.*.W1.Bib6.Rank=8
FR.*.W2.Bib6.Rank=6
FR.*.W1.Bib7.Rank=4
FR.*.W2.Bib7.Rank=2
FR.*.W1.Bib8.Rank=3
FR.*.W2.Bib8.Rank=1

FR.*.W2.Bib2.QU=DSQ

EP.IM=Strict
```

## TXT (compact)

The desktop application stores event data in compact text format by default.
The tabular CSV data for NameList (Entries), StartList, FinishList and FleetList (not in the example)
can be inserted easily with cut and paste.
```
#Params

DP.StartlistCount = 8
DP.ITCount = 0
DP.RaceCount = 2

#Event Properties

EP.Name =
EP.ScoringSystem = Low Point System
EP.Throwouts = 0
EP.DivisionName = *
EP.InputMode = Strict
EP.RaceLayout = Finish
EP.NameSchema =
EP.FieldMap = SN
EP.FieldCaptions =
EP.FieldCount = 6
EP.NameFieldCount = 2
EP.NameFieldOrder = 041256
EP.UseFleets = False
EP.TargetFleetSize = 8
EP.FirstFinalRace = 20
EP.IsTimed = False
EP.UseCompactFormat = True

NameList.Begin
SNR;N1;N2;N3;N4;N5;N6
1000;abc;def;ghi;jkl;mno;pqr
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
StartList.End

FinishList.Begin
SNR;Bib;R1;R2
1000;1;2;3
1001;2;7;4
1002;3;5;8
1003;4;1;7
1004;5;6;5
1005;6;8;6
1006;7;4;2
1007;8;3;1
FinishList.End

#W1

#W2

FR.*.W2.Bib2.QU=DSQ

EP.IM = Strict
```

## Xml

It makes sense to store the event data in XML-format,
if it is to be stored in a blob field of the data base table or served over the web.

```xml
<?xml version="1.0"?>
<FR>
  <Properties StartlistCount="8" ITCount="0" RaceCount="2"
      DivisionName="*" InputMode="Strict">
    <EP K="Name" V=""/>
    <EP K="ScoringSystem" V="Low Point System"/>
    <EP K="Throwouts" V="0"/>
    <EP K="DivisionName" V="*"/>
    <EP K="InputMode" V="Strict"/>
    <EP K="RaceLayout" V="Finish"/>
    <EP K="NameSchema" V=""/>
    <EP K="FieldMap" V="SN"/>
    <EP K="FieldCaptions" V=""/>
    <EP K="FieldCount" V="6"/>
    <EP K="NameFieldCount" V="2"/>
    <EP K="NameFieldOrder" V="041256"/>
    <EP K="UseFleets" V="False"/>
    <EP K="TargetFleetSize" V="8"/>
    <EP K="FirstFinalRace" V="20"/>
    <EP K="IsTimed" V="False"/>
    <EP K="UseCompactFormat" V="True"/>
  </Properties>
  <Entries>
    <SNR oID="1000" N1="abc" N2="def" N3="ghi" N4="jkl" N5="mno" N6="pqr"/>
  </Entries>
  <StartList>
    <Pos oID="1" Bib="1" SNR="1000"/>
    <Pos oID="2" Bib="2" SNR="1001"/>
    <Pos oID="3" Bib="3" SNR="1002"/>
    <Pos oID="4" Bib="4" SNR="1003"/>
    <Pos oID="5" Bib="5" SNR="1004"/>
    <Pos oID="6" Bib="6" SNR="1005"/>
    <Pos oID="7" Bib="7" SNR="1006"/>
    <Pos oID="8" Bib="8" SNR="1007"/>
  </StartList>
  <FinishList>
    <FL>SNR;Bib;R1;R2</FL>
    <FL>1000;1;2;3</FL>
    <FL>1001;2;7;4</FL>
    <FL>1002;3;5;8</FL>
    <FL>1003;4;1;7</FL>
    <FL>1004;5;6;5</FL>
    <FL>1005;6;8;6</FL>
    <FL>1006;7;4;2</FL>
    <FL>1007;8;3;1</FL>
  </FinishList>
  <MsgList>
    <ML>FR.*.W2.Bib2.QU=DSQ</ML>
  </MsgList>
</FR>
```

[message flow](doc-msg-flow.html)