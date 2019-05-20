---
layout: default
lang: en
---

Hi, this is the *documentation* for project FR, see source at [GitHub](https://github.com/federgraph).

Part of the content has been recycled from old blog posts.
It may be outdated by now and removed.
But I want to start with this version, so that it becomes part of the history.

This is currently work in progress, as always.

# FR01

#### An Open Source Application

[FR01](applications/FR01.html) is the program you can use to analyze the event data of a sailing regatta in FR format.

Example: Immediately after the race is done you download the current standing as of yesterday, with button click in FR01.
You be quick and input finish positions of the race just completed.
The application computes the new result, series points and overall ranking.

Then you can change the number of throwouts and have a look.
You could add or remove penalties and of course: *modify* finish positions.
That should be fun.

> Your changes can be posted back to the server if the server does allow this.

FR01 should be made available on several platforms as we go.

#### Just an Idea, your mileage may vary

The data used by FR01 may just be html fragments,
which can be embedded unchanged on the Web site of the event.
This way you don't have text, xml or json, but html. What is special about the html
is that it does contain a complete representation of the data of the event.
So it is possible for a program such as FR01 to read that data and exactly reproduce the results.

While the Html is kept current by the program,
the look in the browser can be independently improved by the designer of the site.

#### Use of static files

For a single event it is enough to post a single static html file to the server.

In the typical case you will have several files,
one html file for each class of boat (the events),
and one xml file, EventMenu.xml would be a good name,
which serves as a list of available content, the event data files,
so that the application will know where the files are.



