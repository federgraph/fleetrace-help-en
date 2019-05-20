---
layout: default
lang: en
title: Schnellstart
---

# FRIA Schnellstart

## Einleitung

If you want to use the FleetRace Internet Application (FRIA) on your website you have to provide the data.
This article is a primer on how to create the xml or txt data.
Talking about FRIA we mean FRIA05.xap,
also referred to in the context of this article as the Silverlight client.

## FR97

The first thing you should probably *get* is [FR97](../applications/FR97.html) which contains:
- the Silverlight client in folder ClientBin
- the example data beneath docroot/Results/
- therein EventMenu.xml, the example data directory file
- and the server application FR97.exe

Following the installation and start of application FR97 you can click to open a browser and load the Silverlight client.

As an experienced computer user you may want to copy the Silverlight client,
the example data and EventMenu.xml to a local web server (IIS, Apache),
just in order to see that it is fully functional there.
In any case you need to fix a URL in WebMenu.xml.
Also you must make sure that the web server is configured for serving up .xap files (see mime type, restart server after change).

Next you can focus on the event data itself.
Perhaps you start by making a copy of the installation folder of FR97 at a writable location.

How you should proceed from here depends on the situation.
The use of FR93 is just a suggestion.

## FR93

[FR93](../applications/FR93.html) FR93 is a easy to use program.
It makes sense to assemble the event data in a spreadsheet,
copy the data via the clipboard into FR93,
check and edit it within FR93 and copy the FR-XML out of FR93 finally.

In order to import data from [spreadsheet](doc-spreadsheet-use.html), 
cut out the data in the spreadsheet then open the import dialog from within FR93 and paste the data into this dialog.
The import dialog has features you use to transform,
select and send the data to the FR93 program in the format expected.

The information held in memory can be output at any time in text and xml format.
Text and xml always correspond to each other completely.
The output is written to the Memo field at page status/reports,
no paper or disc access is needed.

If you see the xml in the Memo control (multi line text box) you can copy it via the clipboard out of FR93 and into a text file.
Now you have the result, which you can edit later to achieve layout customizations.
The core event data should have been *imported* perfectly by now.

## FR94

In contrast to FR93 the feature set of [FR94](../applications/FR94.html) has been reduced even more.
FR94 does no longer contain the race part and cannot output xml, but can still output text.
The Silverlight client is able to read text, the xml format is not mandatory.
For the purpose of publication on the internet and display on different platforms in different countries the xml format is strongly recommended though.
RiggVar Software can help you with the conversion of text into xml.
Possibly a web service is made publicly for this task later.
To test the system at home, the text format is all you need,
and it may be more convenient to handle.

## Schema

Das Schema for the FR-XML is finally defined,
because FR reads, writes and transforms xml data already and the code is not going to change in near future.
The content of the DTD (Document Type Definition) and XSD (Xml Schema Definition) need to express this given situation.
XSD can be provided, please ask.
The provided version of the XSD may change just so it represents the the scenario in the best possible way.
All additional information necessary for adding a FR-XML data export feature
to third party result programs will be detailed in the data [export guide](doc-data-export.html).

## Fazit

With FR97 you can acquire the Silverlight client for testing.
You do not need to configure a standard web server at your computer.
FR97 will use an embedded development web server.
After installation of FR97 you can see something immediately.

With FR94 you can import data from Excel and export FR-TXT.
FR94 was trimmed for easy use.

FR93 contains the race part.
You use the race part to accumulate split times (and finish times) of entries in the individual races.
There are special Silverlight clients for display of race data.
If you are interested in live timing of races you may want to skip FR94 and start with FR93.

In all cases it is possible to create FR-TXT or FR-XML
with the help of a text editor of your choice or a script of your manufacturing.
The examples, the output of FRXX, the XML-Schema, the growing documentation, 
the expert team will help you with that task.

Always keep in mind: if you have much trouble you probably make a mistake.
The system was created with the aim of avoiding hard work where possible.
We think we have come a long way in this regard.
