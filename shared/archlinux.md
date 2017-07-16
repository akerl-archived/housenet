archlinux setup
===============

## Install media

[Archlinux latest ISO](https://www.archlinux.org/download/)

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
passwd # set temporary root password and remember it
pacman -S --noconfirm grub openssh
systemctl enable dhcpcd
systemctl enable sshd
echo "PermitRootLogin yes" >> /etc/ssh/sshd_config
grub-install /dev/sda
grub-mkconfig -o /boot/grub/grub.cfg
```

### Finish up

Exit the arch-chroot shell with Ctrl-D and reboot

