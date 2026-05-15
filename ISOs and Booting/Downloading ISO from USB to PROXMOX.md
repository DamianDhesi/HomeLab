plug in usb and find the usb drive
```
lsblk
```
- will show the drive names and their sizes
- find the usb name based off the size show for each drive
	- ex: sda1

mount drive on /mnt (dir for mounting, but can make a new dir and mount there)
```
mount /dev/<drive_name> /mnt
```

copy iso from /mt to /var/lib/vz/template/iso (dir for storing isos)
```
cp /mnt/<drive_iso> /var/lib/vz/template/iso/
```

unmount drive
```
umount /mnt
```

