jumpbox bootstrap
=================

## OS

https://archlinuxarm.org/platforms/armv6/raspberry-pi

## Initial config

ssh to the server w/ the default user/pw, and run the following:

```
su -
passwd # Pick a strong password
pacman -Syu vim-minimal git puppet
echo "PermitRootLogin yes" >> /etc/ssh/sshd_config
systemctl restart sshd
```

Close your current SSH session and log in as "root"

````
userdel alarm
rm -rf /home/alarm
mkdir /opt/halyard
git clone --recursive git://github.com/halyard/goblin /opt/halyard/repo
```
