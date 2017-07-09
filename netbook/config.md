netbook config
==============

## Install media

Ubuntu LTS server i386 ISO

## Install steps

1. Select US/English at the multiple concurrent prompts
2. Keyboard layout: English (US)
3. Hostname: infra
4. Username: Les Aker / akerl / good password
5. Disk partitioning: yes unmount stuff, Guided w/ LVM (encrypted)
6. Put in a legit LUKS passphrase
7. Keep hitting OK until it installs the system
8. No package mirror
9. No automatic upgrades
10. Standard utils and OpenSSH server
11. Install GRUB to MBR on /dev/sda

Reboot

## Puppet setup

Log in as root and do the following:

1. `curl -sLo kickstart https://git.io/goblin && bash kickstart`
2. `apt install linux-generic-hwe-16.04`
