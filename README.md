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
