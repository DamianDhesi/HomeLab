put 
```
Enabled: false
```
- in the pbs-enterprise.source file in /etc/apt/sources.list.d if no subscription

can add free community updates file
```
Types: deb
URIs: http://download.proxmox.com/debian/pbs
Suites: trixie
Components: pbs-no-subscription
Signed-By: /usr/share/keyrings/proxmox-archive-keyring.gpg
```