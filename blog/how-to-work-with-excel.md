---
layout: default
lang: en
title: Working with Excel
---

# How to work with Excel

You can prepare data for the FR Event in Excel and copy it over to the FR-TXT result file.

The only problem you may face is that the data Excel is exporting to the clipboard is delimited by the Tab character, 
where FR-TXT expects a semicolon as delimiter.

But this should not stop you from using Excel:
- Select the tabular range in Excel
- Copy it to the clipboard (Ctrl C)
- Open Notepad and paste the data (Ctrl V)
- Place the cursor in front of a tab character
- Select the Tab character (Shift + right Arrow)
- Copy the Tab character to the clipboard (Ctrl C)
- Open the Replace dialog (Ctrl H)
- Paste the Tab character into the upper edit box (Ctrl V)
- Press Tab to select the lower edit box (or use mouse)
- Enter the semicolon (;)
- Replace all with button and close dialog

Now you can copy and paste the data from Notepad to the target spot in the FR-TXT file.

> If you paste Excel data into FR01, you only have to press the semicolon-button; 
the tab characters will automatically be replaced.

