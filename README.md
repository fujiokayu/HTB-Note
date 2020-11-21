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
