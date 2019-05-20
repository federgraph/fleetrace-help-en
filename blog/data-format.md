---
layout: default
lang: en
title: data format
---

# Data Format

FR uses 4 different data formats:

1. **Canonical text** is useful if you send single line timing messages via the network to the program.

2. **Compact text** will be smaller in size and will allow you to paste data from Excel into the source text file.

3. **Xml** seems to be most appropriate when you are publishing data on the web in utf-8 format, 
with byte order marker, without encoding and/or line ending problems across the World Wide Web.

4. **Html** is an html5 fragment. Just box this into a valid x-html document 
and use an xml parser to transform the data to canonical text format internally.

No matter what format you use, these are all convertible without loss.

The right format is needed for the purpose; there is no single best format. 
I like the idea of a convertible set of formats, based only on the necessary content.

FR was designed around very efficient single line text messages to be sent over the network. 
The important thing is that the data format is open. 
You can build components that work together with FR01.
