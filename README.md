# VPN-Autoconnect
VPN Autoconnect is a shell script with systemd service based on network-manager that enables your VPN as soon as you get an internet connection



## IMPORTANT

This tool can only connect vpns that are configured using network-manager!



## Usage:

1. Copy vpn-autoconnect to /usr/bin/
2. Edit vpn-autoconnect.service line 10 to your preferences<br/>
   The first parameter after vpn-autoconnect is the name of the network you want to connect to<br/>
   The second parameter is the number of reconnect tries if the connection fails the first time<br/>
   The third parameter is the update interval of the network connection check in seconds
3. Copy vpn-autoconnect.service to /etc/systemd/system/
4. Open a terminal window and type:<br/>
   sudo systemctl enable vpn-autoconnect
5. If you want to turn off the service temporarily run:<br/>
   sudo systemctl stop vpn-autoconnect
6. If you want to turn off the service completely run:<br/>
   sudo systemctl disable vpn-autocomplete



## Debug:

If the program is not working as it should you can try the following things:

1. Open a terminal window and run the program manually by typing:<br/>
   vpn-autoconnect 'name of network' 'number of reconnect tries' 'update interval in seconds'<br/>
   Now a blinking cursor should appear that displays all errors that occure
2. Look at the systemd status by running the following command in the terminal:<br/>
   systemctl status vpn-autocomplete
3. Looking at the log file by running the following command in the terminal:<br/>
   journalctl -u vpn-autoconnect
