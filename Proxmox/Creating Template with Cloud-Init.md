## Create a VM
1. create a new vm
2. set vm to high id to seperate from regualr vms (900+)
3. set OS to not use any media
4. set qemu agent in system
5. delete default disk
6. set desired cpu and ram
7. keep default network bridge
8. finish

## Adding Cloud Init
1. go to hardware and add a Cloudinit drive
2. go to cloud init tab and set up tempalte
	1. user
	2. pass
	3. good to set ip to dhcp, can set static ip if desired
3. press regenerate image

## Set Up Drive
1. get cloud image for desired OS
	1. ex: [latest debian 13](https://cloud.debian.org/images/cloud/trixie/latest/)
	2. qcow2 is preferable as that is most compatible with proxmox 
2. can open a shell into the proxmox host with the created VM and use "wget" using the url for the image to download it
	1. good to rename it something easier
3. run
```
qm importdisk <VMID_of_templae> <cloud_image> <storage_name>
```
4. image will now show up as an unused drive in hardware tab
	1. can delete cloud image now, if desired
5. add the unused disk 
	1. using SATA with SSD emulation and discard is good for thin provisioning 
6. will need to go into options and change boot order to boot from the drive first
	1. can get rid of the CD since there is nothing on it

## Qemu-Agent
1. run
```
sudo apt update && sudo apt upgrade
```
2. run
```
sudo apt install qemu-guest-agent
```
3. shutdown VM via shutdown button in proxmox
4. start vm
5. to check if qemu-guest-agent is now working, run 
```
sudo systemctl status qemu-guest-agent
```
6. good to reset machine id with
```
cat /dev/null > /etc/machine-id
```
7. run 
```
cloud-init clean
```
8. can shutdown VM with shutdown button in proxmox or run
```
systemctl poweroff
```

## Create/Use Template
1. Can right click on the created VM to now turn it into a template
2. can clone template to create a VM based off it
	1. linked clone shares some storage with template 
	2. full clone can be moved to another storage
3. can clone to a different proxmox host in the cluster if the target and template have a shared storage 
	1. if there is no shared storage, you will have to clone the vm to the template host and then migrate the vm to the target host