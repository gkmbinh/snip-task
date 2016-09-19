==============
xorg-edgers fresh X crack
==============

Got error somethings like.
::
  #he following packages have unmet dependencies:
  ibcheese-gtk23 : Depends: libclutter-gtk-1.0-0 (>= 0.91.8) but it is not going to be installed
                     Depends: libcogl15 (>= 1.15.8) but it is not going to be installed
  libcheese7 : Depends: libclutter-gst-2.0-0 (>= 0.10.0) but it is not going to be installed
                Depends: gstreamer1.0-clutter but it is not going to be installed

how to fix
I have added the xorg-edgers PPA again and then properly downgraded with ppa-purge as so,
::
  sudo add-apt-repository ppa:xorg-edgers/ppa && sudo apt-get update
  sudo ppa-purge  ppa:xorg-edgers/ppa && sudo apt-get update

mabe you must install purge 



How to upgrade Ubuntu. 
https://www.digitalocean.com/community/tutorials/how-to-upgrade-to-ubuntu-16-04-lts

How to fix wifi by update install new kernel 4.4 for dell xps 2015
http://blog.jimbasilio.me/2015/12/dell-xps-9350/

