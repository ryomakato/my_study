# Static IP address
- IP address
```
$ sudo ip addr
```
- DNS address
```
$ sudo systemd-resolve --status | grep "DNS Server"
```
- Gateway address
``` 
$ sudo ip route show | tail -n 1
```
Then, modify **"/etc/netplan/01-netcfg.yaml"** or **"/etc/netplan/50-cloud-init.yaml"**
```
# This file is generated from information provided by
# the datasource.  Changes to it will not persist across an instance.
# To disable cloud-init's network configuration capabilities, write a file
# /etc/cloud/cloud.cfg.d/99-disable-network-config.cfg with the following:
# network: {config: disabled}
network:
  version: 2
  renderer: networkd
  ethernets:
    enp0s3:
      dhcp4: no
      dhcp6: no
      addresses: 192.168.1.70/24
      gateway4: 192.168.1.1
      nameservers:
        addresses: 192.168.1.1
```
Finaly, apply the config.: 
```
$ sudo netplan apply
```
