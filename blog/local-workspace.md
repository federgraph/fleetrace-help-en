---
layout: default
lang: en
title: FR Local Workspace
---
        
# Local Workspace

In FR01 you can see the configured data sources in the combo box,
on page Menu in the north container.

This is just a list of Urls. 
For the configured workspace in the first line of the following example you do not need a web server.

```plaintext
C:\Users\UserName\Documents\FRDataDir\EventMenu.xml

http://localhost:8080/FR/EventMenu.xml
```

You can prepend a **Name** which is delimited by an equal sign, 
then this Name will be shown in the combo box instead of the Url. 

And you may choose to prepend the Name by a **star** if you know that the particular workspace is editable. 

```
* Local Workspace = C:\Users\UserName\Documents\FRDataDir\EventMenu.xml
Local Server = http://localhost:8080/FR/EventMenu.xml
```

If you put **stop** on a line, the program will ignore all following lines,
and not use the hard coded example-urls.

```
* Local Workspace = C:\Users\UserName\Documents\FRDataDir\EventMenu.xml
Local Server = http://localhost:8080/FR/EventMenu.xml
stop
```

Individual lines can be commented out as usual with // or #.

```plaintext
* Local Workspace = C:\Users\UserName\Documents\FRDataDir\EventMenu.xml
# Local Server = http://localhost:8080/FR/EventMenu.xml
// Test Server = http://localhost/WebApplication/EventMenu.aspx
Example Server = http://www.fleetrace.org/EventMenu.xml
stop
```

With the Memo control (on page Workspace within the south container in application FR01) you can manage the Urls. 
A temporary list of Urls (input into the Memo) or just a single Url
can be pushed to the combo without touching the list on the hard disk (in the file).

With button **Save** you can save the list in the Memo control to the hard disc, 
so that it will be used when FR01 application starts up. 
(You need to load the list prior to the Save button becoming enabled.) 
The file must be named `fr-workspace-urls.txt`, 
(for Windows) it must be located in folder `AppData/Local/Riggvar/FR`, 
and it will be created automatically by FR01.
Use the clip board to copy a current list of Urls into the Memo control. 
It makes sense to test Urls in Explorer or in the Browser before you use it in the application.

FR01 was originally designed as a program that does NOT save anything to disk,
but then the option was added to allow the user to self manage the list of Urls,
so that you have the flexibility you need.

It is Open Source, you can build yourself a version that does not read from disk,
and which has hard coded Url to your server.

