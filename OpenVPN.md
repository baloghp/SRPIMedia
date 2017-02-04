


````
sudo apt-get update
sudo apt-get upgrade


sudo apt-get install openvpn
cd /etc/openvpn
````


Copy openvpn files
Sample

````
client
dev tun
proto tcp
remote frank.gr.torguardvpnaccess.com 443
resolv-retry infinite
nobind
persist-key
persist-tun
ca ca.crt
remote-cert-tls server
auth-user-pass auth.txt
comp-lzo
verb 1
reneg-sec 0
fast-io
# Uncomment these directives if you have speed issues
;sndbuf 393216
;rcvbuf 393216
;push "sndbuf 393216"
;push "rcvbuf 393216"

# this stuff changes the routing behaviour
script-security 2
;route-noexec
route-up /etc/openvpn/scripts/route_up.sh
route-pre-down /etc/openvpn/scripts/route_down.sh
down-pre /etc/openvpn/scripts/route_down.sh
down /etc/openvpn/scripts/route_down.sh
````


route_up.sh

````
#!/bin/sh
echo 'HELLO: bring up VPN  depending apps'
exit 0
````


route_down.sh

````
#!/bin/sh
echo 'HELLO: bring down VPN  depending apps'
exit 0

````

auth.txt

````
VPNUsername
VPNPassword
````


````
sudo chmod go-rwx auth.txt
sudo crontab -e
````

Add line

````
@reboot sudo openvpn --daemon --cd /etc/openvpn --config VPNFile.ovpn
````


