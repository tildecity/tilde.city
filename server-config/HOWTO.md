Server Setup HOWTO
==================
This here is the transparency part of tilde.city!  If you have any questions,
things aren't clear, etc, just ask, via e-mail or in a GitHub issue.

Just to be different we're using VPSes from cloudatcost.com - one awesome
feature is that they provide servers for a single one-time payment!  But
there are some restrictions, and they're not the highest-powered boxes, but
that's okay for a community like this.

Here's the basic steps to get going.

* change root password
* drop in root ssh key
* test root ssh key
* turn off password authentication
* `userdel user` (backdoor user for support?)
 * `rm -rf /home/user`
* edit `/etc/hostname`
* replace `/etc/motd`
* replace `/etc/apt/sources.list`
* `apt-get update && apt-get dist-upgrade` (this will take a while)
* `apt-get remove mpt-status`
* `apt-get autoremove`
* reboot
* Set timezone to UTC
 * `dpkg-reconfigure tzdata`
 * Select "None of the above" then "UTC"
* Install software
 * `apt-get install unattended-upgrades`
 * `echo 'APT::Periodic::Unattended-Upgrade "1";' > /etc/apt/apt.conf.d/02periodic`
 * `apt-get install csh zsh`
 * `apt-get install emacs joe`
 * `apt-get install ident2 mosh nginx rsnapshot sudo tmux ufw znc`
 * `apt-get install alpine elinks finger htop git irssi lynx talk talkd`
 * `apt-get install golang`
* edit `/etc/joe/joerc` and enable -nobackups (personal preference)
* set up firewall
* set up `/etc/skel` (see provided files)
* `useradd -D -s /bin/bash` (sets bash as default shell)
* set up your admin user's account
* set up sudo for your admin user
* stop using root directly! :)
* set up nginx

Admin Server
------------
* `apt-get install ircd-hybrid`
* `apt-get install puppetmaster`
* configure exim to accept mail for tilde.city from the Internet