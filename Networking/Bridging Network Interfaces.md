Primarily useful when trying to get internet from one network interface to another 
- ex: bridge wifi and ethernet interfaces on device = all hosts connected through device on ethernet will now have internet access
- bridge essentially functions like a switch (layer 2)
	- DHCP traffic can pass through which can be nice as all hosts on the receiving end of will be considered part of the greater network (hosts bridged to a 10.1.1.0/24 network will receive IPs from that network)
	- Allows devices on both sides of the bridge to communicate with each other
		- If not desired, then using [Internet Connection Sharing (ICS)](https://en.wikipedia.org/wiki/Internet_Connection_Sharing) will turn the device into a router (layer 3) and put all the devices connected to the device in their own network


## Easiest Method of Bridging
1. Throw a supported version of windows (any of Windows 7+) on the device with a wifi interface and an ethernet interface
	1. Can also bridge ethernet to ethernet if desired
2. Go to control panel
3. search and select network and sharing
4. select change adapter settings
	1. if sharing is enabled on the wifi interface
		1. will need to right click on wifi interface
		2. select properties
		3. select sharing tab
		4. unselect the top tick box to disable sharing
5. select both Ethernet and wifi interfaces
6. right click and select bridge connections
7. hosts connected to ethernet interface will now be connected to the wifi network
	1. may need to assign a static ip from the wifi network to the bridge adapter if it isn't working immediately

It is likely possible to perform bridging on Linux distributions (through some form of using NetworkManager/netplan, arp-proxy, etables, etc.) however it takes significantly more effort than creating a bridge through control panel on Windows 7 or higher
- may not even be possible to bridge a wifi interface with an ethernet interface on some OSes but this is uncertain 