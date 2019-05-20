---
layout: default
lang: en
title: Use Cases
---

[Skip](../links.html) that it is very old. Now we have Open Source.

## UC 1

> You want to provide results for the Silverlight Client.

Components:
- FR93
- FRIA4
- Expression Web
- static Website

Using FR93 you create the text file or xml file with the results.
The results are uploaded with Expression Web via FTP to the static Website.
A link on a page will load another page with Silverlight Client FRIA4 into the browser.
The Silverlight Client will download and process an EventMenu.xml file from the server,
and single Event.xml files later when the user selects the specific Event. 

The number of EventMenu.xml files and Event.xml files that are managed by the Website is not unlimited.
If a constant number of events are created und reused, then the EventMenu.xml may remain unchanged.
Updating an event is reduced to uploading the specific Event.xml file.

## UC 2

> You want to provide results to the Desktop Client.

Components:
- FR93
- FR94
- Web Editor (Visual Studio Code)
- static Website

It works the same way as in UC 1,
except that you do not need a license for the Silverlight Client.
Expression Web can be replaced by something else.

## UC 3

> You want to minimize cost as much as possible.

Components:
- Spreadsheet and text editor
- FR94
- Expression Web
- static Website

It works as with UC 2,
except that you only use the Spreadsheet, the text editor, or FR94 itself to create the data files.
You could of course export the text files from another result program.

## UC 4

> You operate a team homepage and want to integrate results - from the events you participate in.

Components:
- none

It can be setup such that the data and the Silverlight Client will be loaded from another site.
Then all that needs to be done is include a snippet of Html with the object tag for the Silverlight Client into the hosting Html page.
The matching EventMenu.xml and Event.xml files will be provided on the other Website.
Make sure that there is someone who cares about the results.
Provide the input data to them.

## UC 5

> You want to receive live data of the race.

Components:
- FR38
- FR04
- FRIA4

Use FR38 to send timing messages to the FR04 server.
These messages can be received and processed by FRIA4, the Silverlight application.

## UC 6

> You want to receive live data of the race, but as direct as possible and with minimal effort.

Components:
- FR38
- FR92

Using FR38 you send timing messages directly to FR92. Connect as many sender instances as needed.

## UC 7

> You want to download the current state from the central system and store it locally.
 
Components:
- FR92 (central system)
- FR91 (any number)

FR92 plays the role of the Bridge Server.
FR91 can connect to FR92 as a Bridge Client and request data.
FR91 as a Bridge Client can also send data, e.g. update penalties.

## UC 8

> You want to use an existing FR04 server for UC 7.
 
Components:
- FR91 (Master)
- FR04 (Server)
- FR91 (any number)

This way you collaborate and work together on the same event.
Make sure that at least one party does save the work, and don't forget to make backups frequently.

## UC 9

> You want to request normal Html pages showing the current state.
 
Components:
- FR91 (Client)
- FR04 (Server)
- Browser (many)

Use FR91 as Bridge Client and send data to FR04 (Upload).
FR04 has a built-in Webserver.
Just point your browser to the server and request pages from FR04.

# UC 10

> You want to run UC 9, but are not impressed with the design of the pages.
 
Additional components:
- Web editor

You need to work on the design aspect and provide your own template.

## UC 11

> You already use UC 1 with success and now want to include the sponsor logo on the Silverlight Client.
 
Components:
- Logo
- Visual Studio oder Expression Blend

You have licensed the Silverlight Client already.
RiggVar Software will create another version of it with the sponsor logo included.
You can design the UI surface yourself if you want, we will add the functionality (code behind). 

# UC 12

> You are interested in the timing part and want to use the system in school.

Components:
- FR38
- FR95

Use FR38 to send timing messages directly to FR95.
It works with FR04 or FR92 too.
Any number of sender stations can be connected.

# UC 13

> You manage data for many events and need more dynamic management.

Components:
- Visual Studio 2010
- ASP.NET Website
- database

RiggVar Software provides a prototype of an ASP.NET MVC application.
You can manage users and workspaces, upload event data and more.
The Event-Website can be implemented with Ruby on Rails very similarly. 

## UC 14

> You want to use the data of an existing tracking system and see the timing data in the Silverlight Client.

Components:
- Interface specification
- Adapter (to be done)
- FR04
- FRIA4

The integration can be done as a pilot project.
You can count on the help of RiggVar Software.
Alternatively you can do it all by yourself,
because the protocol of the data transmission in system FR is open.

## UC 15

> You want to use the Browser for the timing and see the timing data in the Desktop Client.

Components:
- Browser with javascript
- FR04 (with customized security)
- FR91

There are examples for the JavaScript timing widgets.
A good network connectivity is necessary, usually only available in an Intranet scenario.
FR91 uses the client bridge to connect to FR04. 

Other combinations are possible.

[Top](#)