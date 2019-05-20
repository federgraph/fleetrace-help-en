---
layout: default
lang: en
title: Names
---

# Entry Names

## Intro

The example data files do not include names.
This will reduce the size of the files.
For real use you will need provide the first name,
last name, country, club of entries and display these pieces of text on the reports.
In this article I will show you how to setup the entries table of entry names,
and how to specify some display options.
More information on how to fill the table with data is given
in the [spreadsheet use](doc-spreadsheet-use.html) or [data export](doc-data-export.html) topics.

## Entry Name Table

### Table

For the purpose of displaying names inline,
an entry in a race/event can always look up the names via the SNR (number, foreign key) in the standalone entries table.

You maintain the entries table independently of the race and/or event data,
and you connect the tables by maintaining the SNR value in the race and event tables.
The SNR must be unique.
Do not confuse the SNR (Stammdaten-Nr., Sportler-Nr., primary key) with the Sail-Nr.
The SNR is always a whole positive number.

In many cases you should store the real sail number in a normal column of the entries table,
as a string that may have an alpha part.
In other cases you could prefer to use the numeric sail number as SNR.
In all cases I want you to understand the meaning of SNR as a link between the entries table and the race and event tables.

Updates to the entries table will become visible when the grid is refreshed the next time.
Don't worry about speed, this happens in a timed manner,
you need to show patience for one second.

Currently, the entries table exists in memory of the program.
If the program is not running, the information is stored in a text or xml file,
together with other data for the event,
in the file system or in a blob field of a database table.

### Rows

You can forgo the input of names entirely or always use the same complete superset of content for the entries table.
You do not need to input/update the entry names to start timing the event or compute results.
There is a lot of freedom in regard to how you want to work with athlete/entry names.

By default, no rows are present in the table. You have to press the Add button to add a row in the graphical UI.

A note: The grid used to display data always shows at least one data line, even if in reality the data store is empty.
This line looks like an empty line ready for input,
but you have to press the Add button to insert at least one real row before you start to input data.
(Look for an invalid SNR of 0 to detect the fake row in the UI.)

If messages are sent to the program with updates to the entries table,
a new row is added automatically if no row is present in the table having the specified SNR.

### Columns

The count of columns can be increased by specifying a value for event property FieldCount.
By default, six columns are used.

All data columns (and cells) are equal. They all have the same data type of string.
All cells have the same capacity,
this is independent of the displayed width.
However, when the input is validated,
the length can be limited as needed for each column.

## Event Properties

### EP.NameSchema

Schema NX is the standard, where the name columns are referred to with N1, N2, N3 and so forth.
The count of columns is six by default and can be specified in property FieldCount.

The original schema (Default) has exactly six columns named FN (N1,FirstName),
LN (N2,LastName), SN (N3,ShortName), NC (N4,NOC), GR (N5,Gender) and PB (N6,PersonalBest).
This naming schema is in most cases sufficient.
The column captions can be changed as needed.

The LongNames schema corresponds to the Default schema,
with one difference in that the long column names are used when writing out messages.
In general, the schema is controlling the output of data and not the input of data.
You can always send messages to the program that use the NX schema to define the target column.

An increase of the column count is possible no matter what schema is specified.
The additional columns need to be addressed with NX, starting from index 7.

In future the NX schema should be preferred,
because this one makes it clear that all columns are equal behind the scenes.

A message of `FR.*.SNR1000.N1=A`, when sent to the program,
has the same effect as message `FR.*.SNR1000.FN=A` and would update the first name of the entry with SNR 1000 to A.

### EP.FieldMap

There is a virtual column DN (DisplayName). Property FieldMap controls what values are projected into this column.

The line EP.FieldMap=SN would map the DN column to column SN (N3, ShortName).
Should the DN column be shown in a report, the data of the ShortName column would appear in the column.

The trick is, that some easy to do column content combinations can be done by evaluation of the FieldMap property.
The line `EP.FieldMap=LN,Komma,Space,FN` would put into the DisplayName what you expect.

### EP.FieldCaptions

The FieldCaptions property is used to override column captions of the name columns on the reports.
The default value of NX will be replaced by what you specify.
The value of the property is a comma separated list of captions.
The first item will appear as the caption of the name column displayed first in the report.
The count of items in the list is expected to match the NameFieldCount property.
Additional items/values would be ignored, but would be used again,
if you later increase the value of the NameFieldCount property.
You do not have to always delete everything while you are testing out configurations.

### EP.NameFieldCount

NameFieldCount is the count of name columns that should appear on the reports.

### EP.NameFieldOrder

Property NameFieldOrder controls the order of name columns on the reports.

- It is a short list of digits.
- The list defines the order of columns by listing the index values of the columns, without separators.
- The list should have the length of NameFieldCount items, but can be longer.
- Surplus values will be ignored.
- The default value for the property is 041256.
- This would display columns DisplayName, NOC, FirstName, LastName, Gender and PersonalBest in this order.
- Column DN (DisplayName) has index 0.
- Other columns have index X according to the column identifier NX.

Example follows:
```
EP.NameSchema =
EP.FieldMap = SN
EP.FieldCaptions =
EP.FieldCount = 6
EP.NameFieldCount = 2
EP.NameFieldOrder = 041256
```
The interpretation of the example is as such:

- Name schema NX is used, because it is the standard.
- Virtual column DisplayName points to the SN column.
- The default column captions are used.
- The entries table has six columns.
- NameFieldCount=2 means that two columns are displayed on the reports.
- Displayed columns are column DisplayName (Index 0) and column N4 (Index 4) in this order.

This will result in the display having the original look.
In most cases there is only space for two columns on the reports.
You should fill the narrow column N4 (NOC) with information that is always to be displayed.
The column DisplayName, which is displayed by default a little bit wider,
should be mapped as appropriate as possible
to the information that happens to be present in the entries table.

## Conclusion

The names are held in the entries table all within memory of the application.
With specific adjustments of properties, reasonable results should be achievable.
It helps if a little bit of planning is used when filling the entries table with data.

The grid used in the graphical UI does not have all the features you may have seen somewhere else.
It is a simple grid,
which is available on all target platforms having the same specified features at no extra cost.
I addition, this grid supports network mode,
meaning that the network features of the program always have high priority.

For all master class graphical reports that are using additional external data sources
and provide live links to other information on the web,
you should use a connected report client to generate them.
The primary data feed for these reports is provided by the FR program online in the form of Xml.
Using that you are in no way limited,
and I hope you will use the flexible design of the FR application to bring out good looking results.
