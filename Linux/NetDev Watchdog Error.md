When using ethernet with linux, it may happen that the device will get spammed with NetDev Watchdog Errors stating the transmit queue for the ethernet interface timed out
- this means that some error has occurred with the ethernet driver and rebooting the device may or may not temporarily fix the problem

can check ethernet controller with
```
lspci -nnk | grep -A2 Ethernet
```

## Intel Controller on Proxmox
In this case the common fix is to turn off TCP segmentation offload (TSO), generic segmentation offload (GSO), and generic receive offload (GRO) off for the NIC in question. This can be done in /etc/network/interfaces
ex:
```
iface nic0 ient manual
	post-up /usr/sbin/ethtool -K tso off gso off gro off
	
auto vmbr0
iface vmbr0 inet static
	addresss 10.11.12.13
	gateway 10.11.12.1
	bridge-ports nic0
	bridge-stp off
	bridge-fd 0
	post-up /usr/sbin/ethtool -K tso off gso off gro off
```

## Realtek Controller
The base r8169 ethernet driver that comes with linux may or may not be stable with a Realtek Controller. In this case installing, the proprietary r8168 driver will be necessary
- will require internet access which can be achieved by using an ethernet to usb cable as the driver will work in that scenario
- best to bring down the ethernet NIC "ip link set nic0 down" to stop the error spam

Steps
1. add the non-free repositories to /etc/apt/sources.list
```
deb http://ftp.debian.org/debian bookworm main contrib  
deb http://ftp.debian.org/debian bookworm-updates main contrib
```
2. install the r8168-dkms package (installing pve-headers may help if using proxmox)
```
apt update
apt install pve-headers
apt install r8168-dkms
```
3. blacklist the r8169 driver so it won't be loaded
```
echo blacklist r8169 >> /etc/modprobe.d/blacklist-r8169.conf
```
4. reboot into BIOS/UEFI and disable secure boot if not disabled already as it will block r8168 driver from loading
5. if ethernet NIC is no longer showing after boot do the following to get dkms to load the r8168 driver
```
dkms build r8168/<driver_version>
dkms install r8168/<driver_version>
modprobe r8168
systemctl restart networking
```
