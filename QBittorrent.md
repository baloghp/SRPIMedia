


````
sudo apt-get install qbittorrent-nox

````

copy qbittorrent-nox-daemon to /etc/openvpn/scripts

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

