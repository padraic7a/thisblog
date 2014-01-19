---
layout: post
title:  "TOGLinux Class Two"
date:   2014-01-17 
categories: Linux CLI
---

TOG Linux Week Two
=======


* pwd
* cd
* ls
* ls -a     list hidden files  
    ls -l     shows files with attributes: permission string: link count: user owner: group owner: last modified date and time: filename  
    ls -la    list all files, including hidden files, with attributes
* cp file01 file02  
    cp -f     force copy, file 2 is overwritten  
    cp -r dir01 dir02 copy directory  
    cp -rf    copy and overwrite directory wihout asking
* mv file1 file2
* mv dir1 dir2
* mkdir 
* rm        remove a file  
    rm -rf dir1   remove file and directory
* touch     create and empty file i.e. touch file01.txt
* less 'j' goes down, 'k' goes up, Ctrl+D goes down half a screen, Ctrl+U goes up half a screen, '/' searches forward, '?' searches back, '? paste' goes up looking for paste,
* less -N   gives line numbers
* cat file1 file2   catenates the contents of file1 and file2 onto the screen with no gap in between the files

Text Editors
-
* cat
* more
* less
* vi
* emacs

User Administration
-
* /etc/passwd   :   contains all user data
* /etc/group    :   contains all 
* /etc/shadow   :   hashed passwords
* /etc/gshadow  :   hashed group passwords

* $ id: gives all details of group memberships for the user i.e.

`padraic@fedora ~$ id` 

`uid=1000(padraic) gid=1000(padraic) groups=1000(padraic),6(disk),10(wheel),983(vboxusers),1001(bumblebee)`
 
* add, delete and modify users and groups  
you could modify files in the /etc folder but its better to use the built in commands:
- __groupadd \<groupname\>__   :this will give the group the next available group id 
- __groupadd -g \<GID\> \<groupname\>__ :if you want to give them a specific id the system will automatically give them the next available number
- __useradd -m -c 'Luke Skywalker' luke__ : -c creates the full name 'Luke Skywalker', login name luke, -m creates home directory if it doesn't exist, 
- __usermod -a G groupnames groupnames__ : handy for giving priviliges

- Disable user's account  
__usermod -s /sbin/nologin jabba__  Redhat method  
__usermod -s /bin/false darth__     Debian method  

- Delete user's account  
__userdel han__ : delete han's account but not his home directory  
__userdel -r han__  : delete han's account and hist home directory  
__usermod --expiredate 1 leia__ : set expiration date to 1/1/1970  

- Lock out a user  
__passwd -l user__  
-unlock  
__passwd -u user__ : this doesn't stop them ssh'ing in, it just prevents the interactive shell here  

Filetypes and permissions  
-
\-  regular file  
d  directory  
l  link  
c  character device  
b  block device  
 
- next nine characters are the for access permissions

 File       read    write   execute  
 Directory  read    write   execute  
 
- Octal permissions  
1 is execute, 2 is write, 4 is read

The digit order is user :group : other (everyone else)

_So 765 is_: read+write+execute: read+write : read+execute

The default permissions are usually 755 for directories and 644 for files

- Changing permissions:
 
 __chmod u+w file__ : give user write permission
 
 __chmod u-x file__ :take away user's execute permission
 
 __chmod (-R) (ugoal) (+-) (rwxst) \<filename\>__
 
 Examples:
 
chown kirk entreprise  
chown kirk:startrek entreprise
 
-SetUid, SetGid and Sticky Bits  
allows you to run programs as if different users ran them (as root for example)
 
Hard links, soft links  
-
__ln file1 file2__  
create a file2 hard link for file1

This is basically another path leading to the file. it can be thought of as two holes looking into the same box. If we delete file1 file2 still exists with the same content.

__ln -s file1 file2__ :creates a softlink  
if you delete file1, file2 still exists but it doesn't point to anything



Mount points
-

Everything in linux is a file

/dev/sda is first disk

To find out which mount points are available for mounting look in /dev/disk foldery

To see what is currently mounted  
__df__
 

how much space does a directory use?
 
__du -sh \<directory\>__
 
 
