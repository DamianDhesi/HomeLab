need to install proxmox default headers if kernel headers are needed on a proxmox/PBS host
```
apt install proxmox-default-headers
```

then install needed headers based on kernel
```
apt install proxmox-headers-$(uname -r)
```