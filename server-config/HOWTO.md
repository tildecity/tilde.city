Server Setup HOWTO
==================
Just to be different we're using VPSes from cloudatcost.com - one awesome
feature is that they provide servers for a single one-time payment!  But
there are some restrictions, and they're not the highest-powered boxes, but
that's okay for a community like this.

Here's the basic steps to get going.

* change root password
* drop in root ssh key
* test root ssh key
* turn off password authentication
* edit `/etc/hostname`
* replace `/etc/motd`
* replace `/etc/apt/sources.list`
* `apt-get update && apt-get dist-upgrade` (this will take a while)
* `apt-get autoremove`
* `apt-get install joe sudo nginx alpine emacs`
* edit `/etc/joe/joerc` and enable -nobackups (personal preference)
* set up firewall
* set up `/etc/skel`
