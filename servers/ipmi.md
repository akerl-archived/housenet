server ipmi
==========

This requires that you've bootstrapped the system, since you'll need a local admin interface

## Reset the password

Via SSH to the server, install the required packages:

```
pacman -S ipmitool
```

Now load the required module:

```
modprobe ipmi_si
```

And reset the password:

```
ipmitool user set password 2  # enter a strong password
```

