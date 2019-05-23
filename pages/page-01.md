---
layout: default
lang: en
title: Overview
---

# Fleetrace

## Abstract

Fleetrace (FR) is a compact timing and scoring system for sailing.
It has been designed for use by both the participants in a regatta and the race management team.
The idea is that the data is available in electronic form, and each node will compute the results.
Then the consumer of the data can carry out a what-if-analysis on its own, 
i.e. they can change the data.
The system has been built for taking advantage of the network.
When used as intended, the whole process is paperless and done in real time.
Bring your notebook and leave the printer at home.

## Data acquisition

The input of data is done manually with the effective help of tools.
You choose a boat in the matrix of boats and press a key to generate a time for the boat.
This step is repeated for all boats at all marks, at least the finish.
By cooperation of two persons the data input process can be sufficiently productive.
One person will watch the race; the second person will operate the data input program.
In this manner, a handwritten list on paper could also be digitized quickly.
Other means of data input are possible; interfacing with the tracking system can also be done.

## Data Format

All data is given in human readable text or xml format.
The format has been designed so you can make use of your text editor and spreadsheet.
Only the real input data needs to be recorded.
Computed fields are not stored.
The program has a robust parser for the data.
Feel free to edit the data with the text editor of your choice.

## Server

The server is a state carrying Windows application.
No configuration is needed.
You can simply start up the server and it let it run until you no longer need it.
Windows XP or better is required.
Use a fast machine for the server function and allow the program to accept communication from the local network.
If your machine is a notebook with Windows 7 Home Premium, then you are ready to go.
The server is a product.
Only the server program itself gets installed, no database server or similar things.

## Client
The client can be a desktop application or a Silverlight browser application.
A new notebook from Apple is as good as a Windows 7 machine.
It will run on a 5 year old desktop too.
Make sure the Silverlight-Plugin is installed on the client machine.
The Fleetrace client application is a fully enabled application which deserves good screen and keyboard.
The server will serve html pages too.
The design of these pages can be improved to match your taste.

[continue](page-02.html)