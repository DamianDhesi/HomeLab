cat available on Debian based distros

can enable with
```
sudo dpkg-reconfigure unattended-upgrades
```

can check if enabled with
```
cat /etc/apt/apt.conf.d/20auto-upgrades
```

can see what gets auto installed with
```
cat /etc/apt/apt.conf.d/50unattended-upgrades | grep -v //
```
- can edit what gets auto installed by editing the 50unattended-upgrades file
	- default is to install security updates only but can be configured to install all updates and even reboot automatically
