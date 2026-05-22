intended to be done with /etc/fstab but is hard to set up
- had the issue of log in failing even though credentials were know to be correct
- opt to just have a script run "mount"ing for the share since running the command worked
	- created a new service with systemd to run the script during boot
	- script set to sleep for a few seconds so that the share is mounted after network connection is established
	- **this is a very hacky set up and not ideal**... but it works and that is all I need it to do for now