---
layout: post
title:  "vim: TOG Linux class 3"
date:   2013-12-15 17:55:05
categories: linux vim 
comments: true
---

vim: Linux class 3
==================

This class was an introduction to the vim editor. I've used it a little previously and can add an edit to a file where necessary but to be honest I've got very little experience with it. 

I know enough about text editors in Linux, or maybe more likely Unix to know that this and emacs are considered the big two. And from the brief look I've had at both vim seems mre user friendly so I was looking forward to this class.

To be honest though I felt overwhelmed by the amount of material.We ran through so much that I found it tough to keep up.

teh main points I took in were

4 modes

navigation - list them



vim is case sensitive so check the caps lock if it doesn't act as expected.

Lines wrap by default.

vi defaults to vim

~ means that the file doesn't exist yet - hasn't been saved
@ at the begining of a line means that its going to be really long

different modes
- normal
- insert
- visual
- command line mode (last line mode)

Normal Mode 
-
navigate with the keyboard

Insert Mode
-
using the keyboard to type text

'i' brings you into Insert mode

Command / Last line mode
-
using ':' to exit i.e. :wq w(rite) q(uit)

hitting ':' brings you into Command Line Mode

trying to write without a filename produces and error about the filename. to give a  filename enter it after ':w' i.e. ':w filename'


Saving and Quitting VIM
-



Last Line Mode Commands
-
:set number     Shows line numbers
:set nonumber   Hides the line numbers
:syntax on      Turns on syntax highlighting, figures out language from filename extension

:r  read (open) a file so ':r filename'
:shell        opens a shell, enter some commands, 'exit' returns you to vim

Insert, Append or Replace Text
-
i    insert text at curser
I   insert text at the begining of the line
a   append text after the cursor
A   append text at the end of the line


Moving the cursor around in Normal Mode
_
- h 
- j
- k
- l 

Moving the cursor arounf by word
-


Using a count
_



Move to the begining or end of a line
-


Move to a specific line in Normal Mode
-

Move to a specific line in Insert Mode
-

Move to a specific line in the Window
-
H   Move to the first line in the Window

Join Lines
-
J   joins the current line to the next one with a space in between
gj  same as above but with no space

Using a count:
3j

Erase
-
x   erase characters under the cursor
X   erase character after the cursor

Replace
-
r   replace the character under the cursor
R   replace the character after the cursor



Change Case
-
~


:digraph


Undo / Redo
-
u       undo previous changes
Ctrl+R  redo previous changes
U       undo / redo changes on previous line that was edited

In vi compatible mode

u       Undo/Redo. Previous change only.

Delete (cut) text d + motion command
-
dw      delete from current character to the end of the word
db      delete to the begining of current word
d0      delete to begining of current word........

Searching for a string
-
/pattern    search for the next match of 'pattern'
?pattern    

Substitution :s
-
Lets you substitute 

Marks 
-
allows you to insert marks/labels in your code - up to 26 of them (letters of the alphabet)


Buffers
-



Visual Block Mode
-


