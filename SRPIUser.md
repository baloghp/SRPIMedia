Create a SRPI user, to replace pi user.
pi user is the obvious attack point so we will delete it and replace with our own. Here is will be called SRPI however, you should pick your own username for this.

````
pi@SRPIMedia:~ $ sudo -i
root@SRPIMedia:~# sudo useradd -m tempuser
root@SRPIMedia:~# sudo passwd tempuser
Enter new UNIX password:
Retype new UNIX password:
passwd: password updated successfully
root@SRPIMedia:~# sudo usermod -a -G sudo tempuser
root@SRPIMedia:~# grep sudo /etc/group
sudo:x:27:pi,tempuser
root@SRPIMedia:~# exit
````

````
tempuser@SRPIMedia:~ $ id
uid=1001(tempuser) gid=1001(tempuser) groups=1001(tempuser),27(sudo)
tempuser@SRPIMedia:/etc $ sudo tar -cvf authfiles.tar passwd group shadow gshadow sudoers systemd/system/autologin@.service sudoers.d/*
passwd
group
shadow
gshadow
sudoers
systemd/system/autologin@.service
sudoers.d/010_pi-nopasswd
sudoers.d/README
tempuser@SRPIMedia:/etc $ sudo sed -i.$(date +'%y%m%d_%H%M%S') 's/\bpi\b/srpi/g' passwd group shadow gshadow sudoers systemd/system/autologin@.service sudoers.d/*e sudoers.d             
tempuser@SRPIMedia:/etc $ grep srpi /etc/group
adm:x:4:srpi
dialout:x:20:srpi
cdrom:x:24:srpi
sudo:x:27:srpi,tempuser
audio:x:29:srpi
video:x:44:srpi
plugdev:x:46:srpi
games:x:60:srpi
users:x:100:srpi
input:x:101:srpi
netdev:x:108:srpi
srpi:x:1000:
spi:x:999:srpi
i2c:x:998:srpi
gpio:x:997:srpi
tempuser@SRPIMedia:/etc $ grep srpi /etc/group
````


````
login as: srpi
srpi@192.168.11.40's password:

The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
Last login: Sat Feb  4 19:10:39 2017 from xxxx
srpi@SRPIMedia:~/pi $ sudo userdel tempuser
srpi@SRPIMedia:~ $ ls -al
total 24
drwxr-xr-x 3 1001 1001 4096 Feb  4 20:15 .
drwxr-xr-x 4 root root 4096 Feb  4 20:15 ..
-rw-r--r-- 1 1001 1001  220 Feb  4 19:45 .bash_logout
-rw-r--r-- 1 1001 1001 3512 Feb  4 19:45 .bashrc
drwxr-xr-x 2 srpi srpi 4096 Nov 25 17:57 pi
-rw-r--r-- 1 1001 1001  675 Feb  4 19:45 .profile



````


