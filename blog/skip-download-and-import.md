---
layout: default
lang: en
title: Skip Download and Import
---

# Skip Download and Skip Import

Flags **Skip Download** and **Skip Import** on page Menu have default values,
which are dependent on the mode (Less or More).

These flags control what happens when one of the event buttons is pressed
(after loading a workspace and initializing the event buttons).

Terms Less and More are related to the number of visible buttons.
Every time the mode is toggled between More and Less the flags are reset to their default values.
Only in mode More the flags can be manually set.

In mode Less (when More is visible) both flags are false, so that

- the metadata of the event button is shown in the upper Memo,
- the data of the corresponding event is downloaded,
- the current event is recorded,
- the event is imported into the application,
- and the text of the event is NOT shown in the bottom Memo.

This behavior is fixed and cannot be changed. It is the normal case.
Everything should work, it is intuitive, and you don't need to be concerned about how it works.

In mode More (when Less is visible) flag Skip Import is active by default, so that

- the metadata of the event button is show in the upper Memo,
- the data of the corresponding event is downloaded,
- the current event is recorded,
- the event is NOT imported into the application by default,
- and the text of the event is shown in the bottom Memo by default.

So, in mode More the event will only be shown in the Memo, but not imported into the application.
In mode More you can use the other buttons to test processing steps one by one.

Button Write is always related to the current event.
In mode More you can change the current event (with click on an event button),
without reading the data into the application.
Therefore, it is possible to copy an event between two slots.
To do that, you need to load the event while in mode Less,
then change the current event in mode More,
then save with button Write, provided the new slot is writable.

If you activate flag Skip Download in mode More (which is false by default),
and click on an event button,
the only thing that happens is that the metadata of the events is shown in the upper Memo.
There you can check that the event buttons are set up as expected.

If both flags are deactivated, the behavior is exactly as in mode Less.

So, in mode Less (the production mode) everything is easy as promised.
In mode More (the debug mode) you can examine how the application works.
The rest of the additional buttons in mode More are explained in Article Less or More.
