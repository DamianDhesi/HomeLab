For VMs, running
```
sudo reboot
```
will not affect the uptime reported by proxmox as the proxmox QEMU process is not affected by a "soft" reboot like this
- only way to have the QEMU process restart the uptime on reboot is shutting down and starting back up or restarting through the proxmox UI