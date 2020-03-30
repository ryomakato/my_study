# How to configulate GCP

## 1. ssh
```bash
$ sudo sed -i -e "s/#Port 22/Port 8080/g" /etc/ssh/sshd_config
$ sudo service ssh restart
```
## 2. ufw
```bash
$ sudo ufw enable
$ sudo ufw allow 8080
$ sudo ufw reload
```
GCP上のルーターでもFirewallの設定を変更する
"Compute Engine"=>"VMインスタンス"=>'ネットワークの詳細"=>
[ファイアーウォール ルール]=>[default-allow-ssh]
指定したプロトコルとポート `tcp:8080`

If you want to check attacks from hacker,
```bash
$ cat /var/log/auth.log | grep sshd
```
## 3. config. for local time
```bash
$ sudo apt-get install dbus
$ sudo timedatectl set-timezone Asia/Tokyo
```
## 4. set alart
"お支払い"=>"予算とアラート"

### make password for sudo if you want
```bash
$ sudo passwd root
```
