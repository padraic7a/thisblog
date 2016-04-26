---
layout: post
title:  "Accessing Windows from Fedora"
description: "Accessing a Windows partition through VirtualBox on Fedora."
date:   2014-02-08 
category: articles
tags: [VirtualBox, dual-boot, Windows, Fedora]
---


Accessing Windows from Fedora
=======

My current laptop is a Dell machine and came with Windows 7 preinstalled. I started dual-booting with Fedora shortly after I bought it, soon making Fedora the default option. A while ago I added an ssd and ram to speed up the machine, taking out the cd-rom drive and putting the old hdd in it's place. 

At some stage I made a mess of the Windows partition's mbr. I wasn't too bothered until I tried to do a bit of OCR at home. Tesseract is a well established OCR engine and is available on Linux but none of the front ends I looked at could rival ABBYY Finereader which is Windows only.

After reinstalling Windows on the hdd I wondered if it was possible to access this disk via Virtualbox. It is and I had a go following the tutorials outlined here 
['User-submitted Walkthrough for Windows](http://fds-team.de/cms/articles/2013-12/use-a-real-windows-7-partition-in-virtualbox-kvm-vmware-player-u.html)
and [here](http://geekery.amhill.net/2010/01/27/virtualbox-with-existing-windows-partition/). \[Note to future self, the 'User-submitted Walkthrough for Windows 7' post is what worked for me \] 

Unfortunately the first time i tried using Windows in this way it was dog slow. Although files such as videos could be opened, it took quite some time. One test video file played with fairly unwatchable stutter. Adding Virtualbox additions didn't seem to make any difference.

My initial allocation to the VM was for 1 cpu and 1024M of RAM. Adding two cores makes a little difference but videos were still unwatchable. Upping the RAM to 2048 makes the video work ok, still things still aren't super fantastic.

I had a go at ABBYY using this benchmark, it seemed fairly usable for small corrections. If I was looking to spend any major time on it then booting into Windows would make more sense but using Virtualbox to access the installation could be handy to check something quickly. It's useful to have access to Tresorit until they develop a Linux client.
