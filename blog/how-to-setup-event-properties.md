---
layout: default
lang: de
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

- StartlistCount muss auf 20 gestellt werden, weil der Event 20 Teilnehmer (Entries) hat.
- ITCount muss auf 0 stehen, weil keine Zeiten erfasst werden, nur Zielpositionen.
- RaceCount muss auf 11 gesetzt werden (10 + 1).
- Name ist ein beliebiger kurzer Text und erscheint im Html-Format als Überschrift.
- ScoringSystem kann unverändert bleiben. Das ist ein extra Artikel.
- Throwouts auf 1 bedeutet 1 Streicher und kann vom Programm aus verändert werden.
- ReorderRAF sollte auf False stehen und True nur in Ausnahmefällen (je nachdem wie die Regel ausgelegt werden soll).
- DivisionName = * braucht nicht geändert zu werden, das ist hier immer die richtige Einstellung.
- InputMode sollte auf Strict stehen, wenn die eingegebenen Informationen konsistent sind (eindeutig und/oder fortlaufend), also normalerweise immer.
- RaceLayout auf Finish zu stellen ist die richtige Wahl, wenn Sie Daten eingeben und die Zielpositionen sehen wollen,
  und nicht die Punkte. Kann vom Programm aus geändert werden.
- NameSchema NX ist Standard und für neue Dateien zu empfehlen.
- FieldMap auf N3 bedeutet, dass das Namensfeld N3 auf die Spalte DisplayName abgebildet wird.
- FieldCaptions enthält die Überschriften der Namen-Spalten.
- FieldCount auf 3 bedeutet, dass 3 Spalten gespeichert werden sollen.
- NameFieldCount auf 3 bedeutet, dass drei Spalten in der Event-Tabelle angezeigt werden (kann weniger sein).
- NameFieldOrder 123 bedeutet, dass die drei Spalten in dieser Reihenfolge erscheinen. Es werden niemals mehr als 9 Spalten angezeigt.
- UseFleets muss hier auf True stehen, weil es ein MedalRace gibt.
- TargetFleetSize auf 20 entspricht StartlistCount. Nur im MedalRace starten nicht alle.
- FirstFinalRace auf 11 kennzeichnet hier das MedalRace. Das MedalRace ist das letzte Race nach Abschluss der Qualifikationsrunde, die hier 10 Rennen enthält.
- IsTimed auf False besagt, dass keine Zeiten gespeichert werden. FR01 speichert keine Zeiten.
- UseCompactFormat auf True ist meistens richtig, weil sich die Daten im kompakten Textformat am besten mit dem Texteditor bearbeiten lassen.

Ausgehend von einem guten Beispiel müssen Sie nur folgende Eigenschaften anpassen: **StartlistCount**, **TargetFleetSize** und **Name**. 
Aus StartList löschen Sie die überzähligen Starter heraus. 
FinishList kann komplett gelöscht werden. Auf FleetList und NameList gehe ich in einem extra Artikel ein. 
Alles Weitere können Sie von der Oberfläche des Programms aus erledigen.

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

Und natürlich ist es noch einfacher, wenn kein MedalRace gesegelt wird!

