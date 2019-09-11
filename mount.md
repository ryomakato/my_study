# Mount Desk
## 1. Check desk
```
$ sudo fdisk -l
```
## 2. Check file system
```
$ lsblk -f
```
## 3. Mount
```
$ mkdir /data
$ sudo mount -t  ext4 -o rw /dev/sda1 /data
```
## Unmount
```
$ sudo umount /dev/sda1
```

or
## 1. Check desk
```
$ sudo fdisk -l
```
## 2. Check fetab format
```
$ cat /etc/fstab
```
## 3. Mount
```
$ mkdir /data
$ sudo echo -e '\n/dev/sdb2 /data auto defaults 0 0' >> /etc/fstab
$ sudo mount -a
```

