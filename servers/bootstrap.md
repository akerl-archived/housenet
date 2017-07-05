server bootstrap
===========

## Install media

Archlinux latest ISO

## Install steps

### Set up the installer environment

```
systemctl start dhcpcd
```

### Set up the disks

Run the following inside a `parted` shell

```
select /dev/sda
mktable msdos
mkpart primary 0 100%
set 1 boot on
select /dev/sdb
mktable msdos
mkpart primary 0 100%
```
Run the following from the shell:

```
mkfs.ext4 /dev/sda1
mount /dev/sda1 /mnt
```

### Install the base system

```
pacstrap /mnt base
genfstab -U /mnt >> /mnt/etc/fstab
arch-chroot /mnt
```

Inside your new chroot shell, run:

```
ln -sfv /usr/share/zoneinfo/UTC /etc/localtime
hwclock --systohc
echo "en_US.UTF-8 UTF-8" > /etc/locale.gen
locale-gen
echo "LANG=en_US.UTF-8" > /etc/locale.conf
echo HOSTNAME > /etc/hostname
echo "127.0.0.1 HOSTNAME.DOMAIN HOSTNAME" >> /etc/hosts
pacman -S --noconfirm vim-minimal
```

Create `/etc/systemd/network/wired.network` with the following:

```
[Match]
Name=enp1s0

[Network]
Address=10.1.10.9/24
Gateway=10.1.10.1
DNS=8.8.8.8
DNS=8.8.4.4
```

Run the following in the shell:

```
systemctl enable systemd-networkd
systemctl enable systemd-resolved
passwd # set a good one
pacman -S --noconfirm grub
grub-install /dev/sda
grub-mkconfig -o /boot/grub/grub.cfg
```

Exit the arch-chroot shell and run:

```
ln -sfv /run/systemd/resolve/resolv.conf /mnt/etc/resolv.conf
```

### Finish up

Now reboot
