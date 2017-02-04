
````
srpi@SRPIMedia:~ $ cd etc
srpi@SRPIMedia:/etc $ sudo nano fstab
````

Add

````
//PCNAME/SHARE /mnt/download cifs rw,username=xxx,password=xxxx,uid=srpi,forceuid,file_mode=0777,dir_mode=0777,nosetuids,noperm,nounix 0 0
````

````
srpi@SRPIMedia:/etc $ sudo reboot
````

````
login as: srpi
srpi@192.168.11.40's password:

The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
Last login: Sat Feb  4 20:19:50 2017 from xxxxxxxx
srpi@SRPIMedia:~ $ cd /mnt/download
srpi@SRPIMedia:/mnt/download $ ls

````
