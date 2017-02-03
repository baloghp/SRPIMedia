Raspberry Installation.

OS: Raspbian Lite

Raspi config: 

cmd: sudo raspi-config
Firts update the raspi-config:
* Advanced: Update
Basic settings we will need:
* Change user password - for security reasons
* Advanced: SSH Enabled - we are going to work headless via SSH connection
* Boot Options: Wait for network at boot - for headless work and for the VPN init scripts to work we need this option on.
