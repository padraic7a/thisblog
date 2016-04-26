updating Imagemagick

server I'm using in work is red hat Entreprise Linux 6. I need to updat the version of Imagmagick I have. Unfortunatley package management means that I'm stuck with the version in the repos

6.5.4.7
Release     : 7.el6_5
Size        : 6.4 M
Repo        : installed
From repo   : rhel-6-server-rpms


this guy gave advice but it didn't work for me:

so i looked some more and found that someone had already sourced all the necessary rpms: http://www.sysadminhub.in/2013/06/upgrade-imagemagick-on-red-hat-58.html

I still need:
libfpx.so.1()(64bit)
libIex.so.4()(64bit)
libIlmImf.so.4()(64bit)
libHalf.so.4()(64bit)
libImath.so.4()(64bit)

The solution was to enable the 'remi' repository from the famille collet : http://blog.famillecollet.com/pages/Config-en and then to 

sudo yum --enablerepo=remi install ImageMagick-last.x86_64 ImageMagick-last-devel.x86_64
