server config
=============

## BIOS

* optimal defaults
* date
* boot feature
    * quiet boot off
    * power button 4 sec
* pci/pnp
    * sr iov enabled
* superio
    * 3f8/irq4
    * disabled
    * com
* remote access
    * serial port: com1
    * utf8
* acpi
    * sci irq enabled
    * headless mode enabled
    * acpi v3
* ipmi
    * lan
        * static
            * 10.0.1.x
            * 255.0.0.0
            * 10.0.0.1
* boot device prio
    * removable drive
    * usb
    * cd
    * network
    * disabled

## RAID

select all drives
create unit
raid 10
f8
y

## IPMI

This section is only necessary if you've lost the IPMI ADMIN password

Boot from Archlinux install and run the following:

```
pacman -S ipmitool
modprobe ipmi_si
ipmitool user set password 2  # enter a strong password
```

