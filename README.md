ubuntu-on-termux
================

what is it
----------
This is a fork of [Debian On Termux](https://github.com/sp4rkie/debian-on-termux) to install Ubuntu on Chromebook.

- a shell script to install [Ubuntu 18.04(bionic)](https://wiki.ubuntu.com/BionicBeaver) via [debootstrap](https://wiki.debian.org/Debootstrap) in a [Termux](https://wiki.termux.com/wiki/Main_Page) environment

how to use it
-------------

- install [Termux](https://termux.com/)
- download `ubuntu_on_termux.sh` from [ubuntu-on-termux](https://github.com/sp4rkie/ubuntu-on-termux) into your termux home directory

        cd /data/data/com.termux/files/home
        apt update
        apt install wget
        hash -r
        wget https://raw.githubusercontent.com/abiosoft/ubuntu-on-termux/master/ubuntu_on_termux.sh

- check the configuration lines near the top of the script for your target architecture, debian version and other preferences
- execute the script

        sh ubuntu_on_termux.sh

- to watch the installation process type

        tail -F $HOME/deboot_debian/debootstrap/debootstrap.log

- if all went well (takes about 30min on the hardware below) a script is created to enter the debian guest system

        $HOME/bin/enter_ubuntu

        Usage: enter_ubuntu [options] [command]
        enter_deb: enter the installed ubuntu guest system

          -0 - mimic root (default)
          -n - prefer regular termux uid (termux-uid)

- sample usage: ubuntu shell (stay in chrooted ubuntu)
        
        bash-4.4$ enter_ubuntu
        root@localhost:~#

- for suggestions or in the unlikely event of a problem just raise an issue [here](https://github.com/sp4rkie/debian-on-termux/issues/new):-)

hardware
--------

- developed and tested on Asus C302 Chromebook

reference
---------

[Debian On Termux](https://github.com/sp4rkie/debian-on-termux)

