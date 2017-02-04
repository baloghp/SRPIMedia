


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

