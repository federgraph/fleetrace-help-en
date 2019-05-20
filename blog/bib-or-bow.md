---
layout: default
lang: en
title: Bib or Bow
---
 
# Bib or Bow

Both terms are used for the same thing.
Bib - the start number - is a common term in the area of sports.
It is used for the timing of the event.

The other key field -  SNR -  is used for more general tasks and is shared with 
table Entries. The Entries table contains additional information not necessary 
for the calculation of the event. The Entries table can be empty.

SNR and Bib must be unique. 
It makes sense to always change the Bib from within the program.
Then it is guarantied that the Bib will update in all tables, `StartList`, `FleetList`, `FinishList`, 
and also in the penalty assignments.

The third key field - the ID - is maintained by the program, used internally, 
and will always be correct. When entering Bib and SNR it is possible to make 
mistakes, which will be color-coded in the grid.

If it is only known later, how the bow numbers will be assigned, you could 
set up the event such that high bow numbers are used first, so that you will 
always have unique values while updating to the real low values.

It is only when the timing is done externally, or the list of timing messages 
will be shared, that you have to use the real bow numbers.

The simulation of timing on page Timing assumes contiguous bib numbers, 
starting from one. You cannot use the timing grid if this is not the case. 
You need to decide if you want to use real bow numbers or your own.

On page Keying you can input any bib number (since update 2).

Don't attempt to map the sail number to field SNR. 
The sail number, e.g. `GBR 1234` should be mapped in a suitable manner to the fields of table Entries. 

The ISAF ID for the Bio database should also go into the Entries table.

If you add lines to table Event with parameter StartListCount or to table 
Entries with button Add, then you have to fill in the key fields. When setting 
up a new event, it is often easier to start from an example, where you only have 
to delete lines.
