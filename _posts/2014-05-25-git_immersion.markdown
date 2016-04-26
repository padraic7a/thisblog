---
layout: post
title:  "Git Immersion tutorial - 1 to 13"
description: " Working through the git immersion tutorial."
date:   2014-05-25 
category: articles
tags: [git, version control]
comments: true
share: true
---

# Git Immersion

Some notes as I follow the git immersion tutorial.

I had been using 

~~~ruby
$ git add . 
~~~
 
to stage every file in the directory for a commit. Instead it might make sense to commit one or more files at a time. So if I have changed files a, b and c I might commit like:


~~~
$ git add a
$ git add b
$ git commit -m "changes for a and b"
$ git add c
$ git commit -m "A different change for c"
~~~


I think I have been guilty of commiting to many random changes, and not having very useful commits as  a result. Lumping changes in different files doesn't help either.



The tutorial makes the point in lab 9 that git tracks changes, rather than files. So you can modify a file, stage it for commital and then modify it again. If you commit now only the staged change is recorded. 


##Lab 10 to Lab 13 deal with history.

###Lab 10
I didn't know about the 

~~~
$ git log -pretty=oneline
~~~  

option, that's pretty nice. the author also goes into some options to limit results by time or author

~~~
--since='5 minutes ago'
--until='5 minutes ago'
--author=<author name>
~~~

###Lab 11

setting some of these options for log layout into aliases and shortcuts
Basically teh author advises putting a bunch of aliases into the .gitignore file. 'hist' is used instead of the heavily optioned log, ci for commit, co for checkout, st for status, br for branch and so on. the author also advises a number of shell aliases - to be honest I fon't think I use git enought for these to be an advantage rather than a hinderance.

###Lab 12- Getting old versions

So after you use  git hist  you're presented with the following:

~~~
* 86a1214 2014-05-25 | added comment (HEAD, master) [padraic]
* 8beb078 2014-05-25 | added a default value [padraic]
* 65514f1 2014-05-25 | using #ARGV      modified:   hello.rb [padraic]
* 8b22702 2014-05-25 | Adding the file for the first commit [padraic]
~~~


To work with the files in one of thos states you execute the following command:

~~~
$ git checkout <7 character hash>
~~~


So from here you either create a new branch or return to the latest modification by:
 
~~~
$ git checkout master
~~~

###Lab 13 - tagging

To create a tag:

~~~
$ git tag whatever
~~~

This tags the current version of the file - or files as 'whatever'.


To list all tags:

~~~
$ git tag
~~~


To delete a tag:

~~~
$ git tag -d whatever
~~~

You can also tag previous versions, first by checking them out, then by 

~~~
$ git tag whatever-1
~~~

Once you have tags for versions you can move betweemn using the tags rather than the hashe values.

~~~
$ git checkout whatever
$ git checkout whatever-1
~~~

To see tags in the logs:

~~~
$ git hist master -all
~~~



 



