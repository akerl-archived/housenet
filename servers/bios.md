server configs
==============

BIOS settings
-------------

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
            * 10.0.2.x
            * 255.0.0.0
            * 10.0.0.1
* boot device prio
    * removable drive
    * usb
    * cd
    * 3ware
    * network

RAID config
-----------

select all drives
create unit
raid 10
f8
y
