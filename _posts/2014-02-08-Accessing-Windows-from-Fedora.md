---
layout: post
title:  "Accessing Windows from Fedora"
date:   2014-02-08 
categories: virtualbox windows fedora dual-boot
---


Accessing Windows from Fedora
=======

My current laptop is a Dell amchine and came with Windows 7 preinstalled. I started dual-booting shortly after I bought it with Fedora as the default. A while ago I added an ssd adn ram to speed up the machine, taking out the cd-rom drive and putting the old hdd in it's place. At some atage I made a mess of the Windows partition's mbr.

I wasn't too bothered untill I tried to do a bit of OCR at home. Tesseract is a well established OCR engine and is available on Linux but none of the front ends I looked at could rival ABBYY Finereader which is Windows only.

After reinstalling Windows on the hdd I wondered if it was possible to access this disk via Virtualbox. It is and I had a go following the tutorials outlined here 
'User-submitted Walkthrough for Windows 7http://fds-team.de/cms/articles/2013-12/use-a-real-windows-7-partition-in-virtualbox-kvm-vmware-player-u.html
and here 
http://geekery.amhill.net/2010/01/27/virtualbox-with-existing-windows-partition/. \[Note to future self, the 'User-submitted Walkthrough for Windows 7' on the http://geekery.amhill.net post is what worked for me \] 

Unfortunatley it's dog slow, files such as videos can be opened, though this takes some time. One test video file plays but with fairly unwatchable stutter. Adding virtualbox additions didn't seem to make any difference.

My initial allocation for 1 cpu and RAM was 1024MB. Adding two cores makes a little difference but videos are still unwatchable. Upping the RAM to 2048 makes the video work ok, still not super fantastic.

I had a go at ABBYY using this benchmark, it seems fairly usable. If I was looking to spend any majr time on it booting int Windows would make more sense but it could be handy to check something. Likewise it's useful to have access to Tresorit until they develop a Linux client.
