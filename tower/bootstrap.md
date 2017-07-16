tower bootstrap
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
mkpart primary 1 100%
set 1 boot on
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
passwd # set a good one
pacman -S --noconfirm grub
grub-install /dev/sda
grub-mkconfig -o /boot/grub/grub.cfg
```

### Finish up

Now reboot
