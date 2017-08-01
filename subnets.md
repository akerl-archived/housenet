# Subnet list

This list was generated using [subnet_slicer](https://github.com/akerl/scripts/blob/master/subnet_slicer).

To update it, [click here](http://www.davidc.net/sites/default/subnets/subnets.html?network=10.0.0.0&mask=8&division=55.ff4628e5605551) to re-open the existing topology, modify it, and then re-run subnet_slicer.rb with the new URL

## 10.0.0.0/24

VLAN 1 / untagged

* 10.0.0.1 - edge - unifi SG
* 10.0.0.2 - switch1 - cisco 2960G
* 10.0.0.3 - wap1 - unifi ap ac pro

## 10.0.1.0/24

VLAN 2

* 10.0.1.2 - infra - rpi3

## 10.0.2.0/24

VLAN 3

* 10.0.2.2 - controller - tower

## 10.0.3.0/24

VLAN 4

* 10.0.3.11 - alpa-ipmi
* 10.0.3.12 - bravo-ipmi
* 10.0.3.13 - charlie-ipmi
* 10.0.3.14 - delta-ipmi
* 10.0.3.15 - echo-ipmi
* 10.0.3.16 - foxtrot-ipmi

## 10.0.4.0/24

VLAN 5

* 10.0.4.11 - alpa
* 10.0.4.12 - bravo
* 10.0.4.13 - charlie
* 10.0.4.14 - delta
* 10.0.4.15 - echo
* 10.0.4.16 - foxtrot

## 10.1.0.0/24

VLAN 10

* Radius auth for trusted devices

## 10.128.0.0/24

VLAN 99

* 10.128.0.2 - jump - rpi

## 10.254.0.0/24

VLAN 10

* DHCP Wifi

## 10.254.1.0/24

VLAN 10

* Static leases for IoT

## 10.254.2.0/24

VLAN 10

* Static leases for games

## 10.255.0.0/24

VLAN 10

* Guest wifi

