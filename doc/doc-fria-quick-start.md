---
layout: default
lang: de
title: Schnellstart
---

# FRIA Schnellstart

## Einleitung

Wenn Sie die FleetRace Internetanwendung (FRIA) auf Ihrer Website einsetzen 
wollen, dann müssen Sie natürlich die Daten bereitstellen. Dieser Artikel gibt 
Ihnen einige Hinweise, wie Sie sofort loslegen können. Mit FRIA ist hier die 
Variante FRIA05.xap gemeint, im nachfolgenden der Silverlight client.

## FR97

Als erstes sollten Sie sich das Paket [FR97](../applications/FR97.html) *besorgen*, welches folgendes enthält:
- den Silverlight client im Ordner ClientBin
- die Beispieldaten unterhalb von docroot/Results/
- darin EventMenu.xml, das Verzeichnis für die Beispieldaten
- und die Serveranwendung FR97.exe

Nach Installation und Start der Anwendung FR97 können Sie mit einem Klick 
einen Browser öffnen und den Silverlight client laden.

Als erfahrener Computerbenutzer wollen Sie eventuell als nächstes den 
Silverlight client, die Beispieldaten und EventMenu.xml auf einen lokalen 
Webserver kopieren (IIS, Apache), um zu sehen ob es dort auch funktioniert. Sie 
müssen auf alle Fälle in WebMenu.xml eine URL anpassen. Stellen Sie außerdem 
sicher, dass der Webserver für die Auslieferung von .xap Dateien konfiguriert 
ist.

Anschließend können Sie mit der Bereitstellung Ihrer Daten beginnen. Am 
besten arbeiten Sie dazu mit einer Kopie des FR97 Installationsordners, an einer 
Stelle, wo Sie Schreibrechte haben.

Wie sie weiter vorgehen, hängt von der Situation ab, die Verwendung von FR93 
ist nur ein Vorschlag.

## FR93

[FR93](../applications/FR93.html) ist ein einfach zu benutzendes Programm.

Ein sinnvoller Einsatz ist dadurch gegeben, 
dass Sie die Wettkampfdaten im [Spreadsheet](doc-spreadsheet-use.html) aufbereiten,
über die Zwischenablage in FR93 einfügen,
in FR93 kontrollieren/weiterbearbeiten,
und zum Schluss das FR-XML aus FR93 entnehmen.

Um Daten vom Spreadsheet zu importieren öffnen Sie den Importdialog und fügen 
die Daten ein, die zuvor im Spreadsheet ausgeschnitten wurden.

Die von FR93 im Speicher gehaltenen Informationen können jederzeit im Text- 
und Xml-Format ausgeben werden. Text und Xml entsprechen sich immer 
vollständig. Die Ausgabe erfolgt im Memo auf Seite Status/Reports.

Wenn das Xml im Memo sichtbar ist, kann es über die Zwischenablage aus FR93 
herauskopiert werden. Damit haben Sie das Ergebnis, das Sie in Bezug auf die 
Darstellung später noch manuell anpassen können. Die eigentlichen Eventdaten 
sollten aber jetzt schon perfekt übernommen sein.

## FR94

[FR94](../applications/FR94.html) ist gegenüber FR93 noch weiter abgerüstet.

FR94 hat der Race-Teil nicht mehr mit an Bord und kann auch kein Xml erzeugen, aber 
immer noch Text. Der Silverlight client kann den Text lesen, Xml ist nicht 
zwingend vorgeschrieben. Für die Veröffentlichung im Internet zur Ansicht auf 
verschiedenen Plattformen in verschiedenen Ländern ist das Xml-Format jedoch 
dringend zu empfehlen. RiggVar Software kann für Sie Text in Xml konvertieren. 
Eventuell wird dafür später auch ein automatischer Webservice bereitgestellt.

Für das Testen zu Hause ist Text völlig ausreichend und eventuell auch einfacher, produktiver zu handhaben.

## Schema

Das Schema für FR-XML ist bereits abschließend definiert, da FR Xml-Daten 
liest, schreibt und transformiert, und der Code dafür nicht mehr geändert wird. 
Die Gestaltung von DTD (Document-Type-Definition) und XSD 
(Xml-Schema-Definition) muss dem entsprechen.

DTD oder XSD wird auf Anfrage bereitgestellt. Die zur Verfügung gestellten 
Versionen von DTD und XSD unterliegen zur Zeit noch dem Änderungsvorbehalt in 
Bezug auf die bestmögliche Darstellung.

Alle weiteren Informationen, die erforderlich sind,
um ein Drittpartei-Result-Programm mit einer Exportfunktion für FR-XML-Daten auszustatten,
sind in der [Export-Anleitung](doc-data-export.html) dokumentiert.

## Fazit

Mit FR97 bekommen Sie den Silverlight client zum Testen Ihrer Daten. Sie 
müssen keinen Webserver auf Ihrem Computer konfiguriert haben, FR97 übernimmt 
diese Funktion. Nach Installation von FR97 können Sie sofort was sehen.

Mit FR94 können Sie in Excel aufbereitete Daten importieren und FR-TXT 
bereitstellen. Diese Anwendung wurde auf einfache Benutzung getrimmt.

FR93 enthält zusätzlich den Race-Teil. Damit können Sie die Zwischenzeiten in 
den einzelnen Rennen erfassen. Für die Anzeige des Verlaufs eines einzelnen 
Rennens gibt es spezielle Silverlight apps. Eventuell sollten Sie also FR94 
überspringen und gleich mit FR93 arbeiten.

In jedem Fall ist es möglich, FR-TXT bzw. FR-XML mit einem normalen 
Texteditor oder mit einem Script aus Ihrer Herstellung zu erstellen. Die 
Beispiele, der Output von FRXX, das XML-Schema, die noch wachsende 
Dokumentation, das Experten-Team
und der Hersteller helfen Ihnen dabei.

Denken Sie immer daran: wenn Sie sich zu viel Arbeit machen, machen Sie was 
falsch. Das System wurde darauf zugeschnitten, Arbeit möglichst zu vermeiden.
