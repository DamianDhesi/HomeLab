repository sources for updates are in /etc/apt/sources.list.d/
- may need to run "apt modernize-sources" on an older distro

can edit .sources files to exclude or include sources

exclude by adding this to top of file
```
Enabled: no
```
- useful for turning off proxmox enterprise/ceph sources if not using a subscription

include by adding this to top of file (unnecessary since default is to include .sources file)
```
Enabled: yes
```


## Update Process
```
apt-get update
apt-get dist-upgrade
apt-get autoremove
apt-get autoclean
```
- dist-upgrade will auto remove packages to resolve dependency changes 
	- full-upgrade has similar behavior, generally preferred over dist-upgrade 
- autoremove automatically gets rid of unneeded packages and autoclean automatically cleans the apt cache