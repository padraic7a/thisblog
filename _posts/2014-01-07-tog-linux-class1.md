---
layout: post
title:  "Starting Linux 1 in TOG Hackerspace"
date:   2014-01-07 
category: articles
description: "My first class on the Linux 1 course in the TOG hackerspace."
tags: [cli, Linux, TOG, course]
---

One of my New Year resolutions is to try and learn some programming this year. I have my eye on python but also want to get some bash scripting under my belt.

After losing interest / momentum on different book or self-study courses and being reluctant to spend tonnes of time on an Irish college course I'be decided to try and take seminars / short courses instead hoping that these would give me enough time and deadlines to get something done without taking over my life.  

Last night was the first class of the six class TOG cli course. It was slow to start since the VirtualBox image didn't't work for attendees. Anyway we went through eh expert install for Debian which was interesting enough. Next week we're going through cd, ls, mv etc etc  

But I did pick up some nice bits and pieces:  

I never knew that running a programme from the command line, if followed by an '&' runs it without it taking over the terminal.  

i.e. 
{% highlight console %}
$gimp&
{% endhighlight %}

runs the programme and generates a number

An image of Gimp&: ![Gimp&](/images/gimp&.png)

The first number, [1] is the job number  
The second number, 3411 is the pid (process identification number). The process can be stopped by 

{% highlight console %}
$kill 3411
{% endhighlight %}

Using the terminal with the '&' 'forks' new the process as a 'child' process. Jaysus I feel like a total 'eejit' writing that.

Debian install
==============

We also carried out a terminal based 'expert mode' installation of Debian, based on having a 20 gig hard drive and 512MB ram.

The configuration chosen was 

* sda1  /      500MB (1 x ram) | 
* sda2  swap   1 GB  (2 x ram) |- all primary partitions
* sda3  /usr   6 GB            |
* sda5  /tmp   500MB
* sda6  /var   4 GB
* sda7  /home  rest of the space 
