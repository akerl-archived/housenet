Archlinux ARM Setup
==================

## OS

* RPi 1: https://archlinuxarm.org/platforms/armv6/raspberry-pi
* RPi 2/3: https://archlinuxarm.org/platforms/armv7/broadcom/raspberry-pi-2

## Initial config

SSH to the server as the `alarm` user, with the password `alarm`. Escalate to root by running `su -` with the password `root`. Run the following to set up and run puppet:

```
curl -sLo kickstart https://git.io/goblin
bash kickstart
```

