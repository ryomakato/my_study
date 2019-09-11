# Samba Installation
This is how to install Samaba.
Reference: [https://tutorials.ubuntu.com/tutorial/install-and-configure-samba#0](https://tutorials.ubuntu.com/tutorial/install-and-configure-samba#0)
## 1. Installing Samba
To install Samba, we run:
```bash
$ sudo apt update
$ sudo apt install samba
```
## 2. Setting up Samba
Now that Samba is installed, we need to create a directory for it to share:
```bash
$ mkdir /home/<username>/sambashare/
```
The command above creates a new folder sambashare in our home directory which we will share later.

The configuration file for Samba is located at /etc/samba/smb.conf. To add the new directory as a share, we edit the file by running:
```bash
$ sudo nano /etc/samba/smb.conf
```
At the bottom of the file, add the following lines:
```
[sambashare]
    comment = Samba on Ubuntu
    path = /home/username/sambashare
    read only = no
    browsable = yes
```

Now that we have our new share configured, save it and restart Samba for it to take effect:
```bash
$ sudo service smbd restart
$ sudo ufw allow samba
```
## 3. Setting up User Accounts and Connecting to Share
Since Samba doesn't use the system account password, we need to set up a Samba password for our user account:
```bash
$ sudo smbpasswd -a username
```
**Connecting to Share**
- ubuntu, mac
```
smb:\\ip-address\sambashare
```
or mount
```bash
$ mount -t smbfs //user@IP_ADDRESS/sambashare   /Volumes/sambashare
```
NOTE: This is how to unmount:
```bash
$ umount /Volumes/sambashare
```
- windows
```
\\ip-address\sambashare
```
