---
layout: default
lang: en
title: Download Example Data
---

# How to download example data

Use FR01. The data FR01 can download will be the EventMenu.xml index file
as well as any number of the EventData.* files containing the data of individual events.

In both cases you can show the content of the downloaded file in the Memo
(multiline edit control) on page Reports.
You will see the source code of the data.
From within the Memo you can then copy and paste the data into notepad and save to disc,
usually with utf-8 encoding selected. Ctrl A (select all), Ctrl C (copy) and Ctrl V (paste)
are the useful key combinations (in Windows and Ubuntu).

If you click the More button on page Menu (in the north container),
additional buttons will become visible, among those the Download button,
which you use to download the EventMenu.xml into the Memo control.
When you see the additional buttons and click on one of the event buttons,
then the corresponding EventData.* file will download and appear in the Memo.
You will see the unprocessed version in the Memo.

`EventMenu.xml` and `EventData.*` can be named differently, only the content is important.
No matter what the format of the file is - TXT, XML, or HTML - they are all text files,
which you can save to disc. Should the downloaded EventData.* be given in format Xml or Html,
then you can still save it as Text,
because program FR01 is able to convert the format without losing information.

In order to convert the format you first have to load the event.
This happens by default when the More mode of page Menu is active.
When loading the data of an event, a strict validation is part of the process.
Output in format Text or Html on page Reports will contain a filtered version of the data,
including the changes you may have already applied
using the grid in the graphical user interface of the application.

When you want to work with you own data, it makes sense to start from a *template*
by downloading a suitable example.

Here is how you may put example data into a local workspace:
- create a folder (e.g. C:\FR\Workspace)
- download EventMenu.xml and save as EventMenuLocal.xml
- download EventData.txt and save as ED01.txt
- edit EventMenuLocal.xml (see below)

On page workspace (in the south container) you can configure access to your local workspace like so:
- press button Load (Memo may now be empty)
- insert line with Url into Memo (top first line recommended)
- press button Save
- merge the new Url into the Url-Combo on page Menu using the button on page Workspace (look on button caption)

The line with the Url in the Memo should look similar to this one:
```
* MyLocalWorkspace = C:\FR\Workspace\EventMenuLocal.xml
```

The * in front of the entry indicates to the program that your local workspace is writable.

Here is how you would modify EventMenuLocal.xml:
- Delete the event data sections that you do not need.
- Leave the path to the images empty, the event buttons in FR01 will only use the name of the event.
- Update the name of any listed event.
- The most important modification is the path. Starting from Root the combined
  values of the path attributes must evaluate to the correct Url of the file.
- Take care of the trailing path delimiter for the root and any subfolders (slash or backslash).

And here is how you could later transfer files from you local workspace to the Web:

Create EventMenu.xml as a copy of your EventMenuLocal.xml in the workspace folder.
In this file you only need to update the path.
The given path entries in the file are relative.
No matter how many events you list in the file,
there will be only minimal modifications necessary when you want to relocate a workspace.
This is the main advantage of the chosen structure for the EventMenu.xml.

Once you have created a local workspace you can use it from within FR01
in exactly the same manner as all other workspaces available on the web,
just with a little more comfort,
because you can work offline and also because the Write button on page Menu will be functional
(if you have marked you workspace with a `*` at the start of the line).

Is it better than constantly wrestling with the File-Open-Dialog?
May be not when you start out,
but later on when you want to push data cost effectively to the Web, it might pay off.
Can you imagine that you will like it? You will, if you like your favorite text editor.
