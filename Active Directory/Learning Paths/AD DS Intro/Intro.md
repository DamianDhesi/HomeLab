Active Directory Domain Services (AD DS) provides a searchable, hierarchical directory and method for config/security settings for objects in an enterprise

## Logical Components
- Partition
	- portion of AD DS database
		- schema partition contains schema, config partition contains configuration objects for forest, etc. 
		- domain partition contains users, computers, groups, and other domain specific objects
- Schema
	- set of definitions of object types
- Domain
	- logical administrative container for objects (users, computers, etc.)
- Domain Tree
	- hierarchical collection of domains that share a root domain and a contiguous DNS namespace
- Forest
	- collection of one or more domains that have a common AD DS root, schema, and common global catalog
- OU
	- container for users, groups, and computers for handling admin rights and linking Group Policy Objects (GPOs)
- Container
	- For organizational use in AD DS
	- Can't link GPOs to containers

## Physical Components
- Domain Controller
	- contains copy of AD DS database
	- all changes are replicated to all other domain controllers
- Data store
	- copy exists on each domain controller
	- Ntds.dit file at C:\Windows\NTDS
- Global catalog server
	- hosts global catalog which is a partial, read only copy of all objects in a multi-domain forest
- Ready-only Domain Controller (RODC)
	- good where physical security is not as good or IT support not optimal
- Site
	- container for AD DS objects specific to a physical location
- Subnet
	- portion of network IP addresses of an organization assigned to computers in a site