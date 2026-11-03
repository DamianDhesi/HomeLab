## Homelabs Notes

General notes and such are included here
- Ansible configs can be found at [my playbook github repo](https://github.com/DamianDhesi/ansible_config)
- Kubernetes manifests can be found at [my manifest repo](https://github.com/DamianDhesi/kub_config)

## Achievements
- Troubleshooting
	- Diagnosed and resolved a Linux ethernet error using the command line, identifying a conflict between the ethernet driver and controller, to restore internet connection to the affected host
- DevOps/Administration
	- Deployed and maintained a three node Proxmox cluster with a Proxmox Backup Server to centralize virtual machine management and recover from tested backups as needed.
	- Implemented configuration management via [Ansible pull using Github hosted](https://github.com/DamianDhesi/ansible_config) playbooks to automate system updates and configure newly created virtual machines
	- Configured Uptime Kuma monitoring to receive immediate notifications on outages affecting virtual machines, Proxmox hosts, and hosted services
	- Transitioned services from Docker/Podman to a Kubernetes cluster on Talos Linux by developing custom YAML manifests for improved ease of deployment and service management
- Networking
	- Deployed Technitium servers providing DNS and DHCP with redundancy to maximize uptime of core network services
	- Set up a Caddy reverse proxy with a Step-CA internal certificate authority using 24-hour TLS certificates with automated renewal to facilitate short lived certifications and TLS offloading
