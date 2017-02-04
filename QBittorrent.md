


````
sudo apt-get install qbittorrent-nox

````

copy qbittorrent-nox-daemon to /etc/openvpn/scripts
modify route up and down scripts


````
srpi@SRPIMedia:/etc/openvpn/scripts $ sudo nano route_up.sh
srpi@SRPIMedia:/etc/openvpn/scripts $ sudo nano route_down.sh
````

route_up.sh

````

#!/bin/sh
echo 'HELLO: take dependent apps down'
qbittorrent-nox-daemon start
exit 0

````

route_down.sh

````

#!/bin/sh
echo 'HELLO: take dependent apps down'
qbittorrent-nox-daemon stop
exit 0

````

````
srpi@SRPIMedia:/etc/openvpn/scripts $ qbittorrent-nox

*** Legal Notice ***
qBittorrent is a file sharing program. When you run a torrent, its data will be made available to others by means of upload. Any content you share is your sole responsibility.

No further notices will be issued.

Press 'y' key to accept and continue...
y

******** Information ********
To control qBittorrent, access the Web UI at http://localhost:8080
The Web UI administrator user name is: admin
The Web UI administrator password is still the default one: adminadmin
This is a security risk, please consider changing your password from program preferences.
04/02/2017 22:18:18 - The Web UI is listening on port 8080
04/02/2017 22:18:18 - qBittorrent is successfully listening on interface 0.0.0.0 port: TCP/6881
04/02/2017 22:18:18 - qBittorrent is successfully listening on interface 0.0.0.0 port: TCP/4433
04/02/2017 22:18:18 - qBittorrent is successfully listening on interface :: port: TCP/6881
04/02/2017 22:18:18 - qBittorrent is successfully listening on interface :: port: TCP/4434
04/02/2017 22:18:18 - qBittorrent is successfully listening on interface 0.0.0.0 port: TCP/6881
04/02/2017 22:18:18 - qBittorrent is successfully listening on interface :: port: TCP/6881
04/02/2017 22:18:23 - External IP: 178.162.201.137


````

Try WEB Interface
http://raspberryIP:8080/#
default login:
UN:admin
PWD:adminadmin




