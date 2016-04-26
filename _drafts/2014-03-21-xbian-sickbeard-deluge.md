---
layout: post
title:  "Xbian, sickbeard and Deluge"
description: "My Raspberry pi setup with Sickbeard and Deluge runing on Xbian."
date:   2014-03-21 17:55:05
category: articles
tags: [raspberry pi, sickbeard, torrents, downloading]
image:
  feature: so-simple-sample-image-2.jpg
  credit: Michael Rose
  creditlink: http://mademistakes.com
comments: true
share: true
---

This is a headline
==================

After spending too mcuh time over tha last couple of week ssettting up my raspberry pi as a torrent downloading box I fried the sd card trying to wedge the pi and hdd into a handy looking, but slightly too small box.

As per usual finding the posts and tutorials I followed initially was a bit of a pain.

writing the xbian image to an sd card can be painful fif you don't dismount the card first: http://www.embeddedarm.com/support/faqs.php?item=10


this post lists some of the packages I need and alsohas someuseful tips on setting up for storing downloads on an external hdd:
http://forum.xbian.org/thread-1018.html


setting up deluge: http://www.howtogeek.com/142044/how-to-turn-a-raspberry-pi-into-an-always-on-bittorrent-box/

This isn't a fully working tutorial - note problems this time round. Some stuff there about priorities which might be useful

some error messagesa bout local settings - LC - went to /etc and edited the environemt file to add LC_ALL="en_IE.utf8"

that didn't seem to work so I tried 
sudo dpkg-reconfigure locales which allowed me to pick en_IE.UTF-8



used the setup described here to have deluge and sickbeard interact nicely:
http://linuxpluse.wordpress.com/2013/12/21/sickbeard-couchpotato-deluge-plex/

Now I need to set up softlinks from sickbeard to the usb, then add shows and then i think I'm set!

ok - I alos need a way for deluged and web ui to start at noot - this doesn't really work from the HTG runthrough

to turn deluge into a service that starts at boot this hand gide and script does the trick: https://docs.google.com/document/d/1cARrPUryp-X37QZy29hCMA3zVddDCg4NmBCIZEflel8/edit
https://www.linuxdistrocommunity.com/videos/?user=quidsup&id=LIUgQEKxjNU









deluge crashing - not continuing as a servoce - maybe back to the htg guide

then a gap, then another line of text gives the paragraph structure

* i think this
* should be a list
* good eh?

I'm blogging with Jekyll for a couple of reasons.
*I like the idea of a static html site vulnerable to less attacks
*I also like the idea of using markdown and it seemd like once you get the hang of it, it should make writing fairly quick
*Finally using Jekyll is an opportunity to use git. 

On the last point:  
I'm hoping to learn a bit of basic programming this year and I know myself enough to know that I need to be learning something implementable. While git isn't programming it is a way to check code out, and maybe alter it, and send the alteration on to someone else. Learning how to commit blog changes isn't the worst start.

So far so not so great on that front though. I tried setting up a `post-receive hook` for deployment ad that didn't work out. I'll try again when I get the hang of jekyll itself.     


Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [My Twitter][@padraicst] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll's Jelly Belly][jellybelly].

[jellybelly]: https://jellybelly.com/‎
[@padraicst]:    http://twitter.com
