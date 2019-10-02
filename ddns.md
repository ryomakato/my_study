# How to configulate of ddclient
You need google domains to config.
Plase check [google website](https://support.google.com/domains/answer/6147083?hl=ja).
## 1. install ddclient
```bash
$ sudo apt update
$ sudo apt install ddclient -y
```

## 2. vim /etc/ddclient.conf
```/etc/ddclient.conf
ssl=yes
use=web
protocol=googledomains
login=generated_username
password=generated_password
your_resource.your_domain.tld
```

## 3. restart
```
$ sudo ddclient -daemon=0 -verbose
$ sudo service ddclient restart
```
