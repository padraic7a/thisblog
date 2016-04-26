---
layout: post
title:  "Logging IRC channels with Irssi"
description: "IRC channels are useful for tech support, but can be distracting when you're working. The time difference also means you can miss out on a lot of potentially useful info so logging is a useful workaround."
date:   2014-05-04 
category: articles
tags: [IRC, cli, Linux,irssi, screen]
---


IRC channels are useful for tech support and picking up info but staying connected when you're working just adds another element to the procrastination-wheel-of-shame. 
Many channels are dominated by North American participants and the time difference means you can miss out on interesting content.

The solution I've found is to log the channels with irssi (a cli irc client) and just connect in to 'live' sessions on Thunderbird when I have a specific question, or am free to contribute.

This requires an always on computer which would have been a barrier in the past but these days I've got my raspberry pi runninng 24-7 for torrents so that's taken care of.

So for future reference here's my setup for doing the following:

* join networks - Freenode and Mozilla
* join specific chatrooms
* set nick \[username]
* record what's said, by whom, along with the time and date

    
so, based on [this blog post][this blog post]

I added a bunch of stuff to the config file in ~/.irssi
I want to auto join a bunch of channels in Freenode and Mozilla, witha a specific user nic (nickname)

In the servers section I added :
{% highlight bash %}

{
    address = "irc.freenode.net";
    chatnet = "Freenode";
    port = "6667";
    use_ssl = "no";
    ssl_verify = "no";
    autoconnect = "yes";
  },
  {
    address = "irc.mozilla.org";
    chatnet = "Mozilla";
    port = "6667";
    use_ssl = "no";
    ssl_verify = "no";
    autoconnect = "yes";
  },
{% endhighlight %}

In the chatnets section I added:

{% highlight bash %}
Freenode = { type = "IRC"; nick = "padraic71a"; };
Mozilla = { type = "IRC"; nick = "padraic71a"; };
{% endhighlight %}

In the channels section I added:

{% highlight bash %}
{ name = "#omeka"; chatnet = "Freenode"; autojoin = "Yes"; },
  { name = "#code4lib"; chatnet = "Freenode"; autojoin = "Yes"; },
  { name = "#projecthydra"; chatnet = "Freenode"; autojoin = "Yes"; },
  { name = "#ruby.ie"; chatnet = "Freenode"; autojoin = "Yes"; },
  { name = "#tog"; chatnet = "Freenode"; autojoin = "Yes"; },
  {
    name = "#guardianproject";
    chatnet = "Freenode";
    autojoin = "Yes";
  },
  { name = "#mozireland"; chatnet = "Mozilla"; autojoin = "Yes"; },
  { name = "#sciencelab"; chatnet = "Mozilla"; autojoin = "Yes"; },
{% endhighlight %}

in settings add

{% highlight bash %}
 autolog_path = "~/irclogs/%Y/$tag/$0.%m-%d.log";
{% endhighlight %}

All of the above sets up irssi to join the correct channels with the correct nick when you join. Irssi still has to be started however. tarting it with screen means that you can have it running and still do other things in the terminal. To start it on boot using 'screen' I followed the instructions at [Nick Geoghegan's blog] [Nick Geoghegan's blog].

These are basically to edit /etc/rc.local and insert:

`/bin/su normal_user_name -c "/usr/bin/screen -dmS irc_logger /usr/bin/irssi"`

That gets everything working as in the image below. Next I want to serve the log files so that I can access then over the network.

![irclogs](/images/irclogs.png)

[this blog post]: http://www.sternwarte.uni-erlangen.de/wiki/doku.php?id=irc:autoscript
[Nick Geoghegan's blog]: http://nickgeoghegan.net/linux/automagically-start-irssi-in-a-screen-on-boot
