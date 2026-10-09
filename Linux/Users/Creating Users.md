### useradd
useradd will create a new user with no password or directory by default
```
useradd <username>
```

to create a home directory for the new user with useradd use
```
useradd -m <username>
```

can specify default user shell with
```
useradd -s /bin/bash <username>
```
- default shell for new users created via useradd will typically be /bin/sh

useradd is nice for created new users for restricting permissions on services/containers
- ex: create a "jellyfin" user for running a jellyfin service. Ensures if an attacker attempts to weaponize the jellyfin service, they are restricted by the permissions of the "jellyfin" user

[debian docs on useradd](https://manpages.debian.org/unstable/passwd/useradd.8.en.html)
### adduser
not available on all Linux distros but works as a soft link to useradd or a Perl script to make an easier user creation experience

```
adduser <username>
```
- will automatically create a home directory for the user
- asks for user password
- asks for user 
	- full name
	- room number
	- work phone
	- home phone
	- other info

similar result can be achieved with useradd
```
useradd -d /home/test -m -s/bin/bash \ -c FullName,Phone,OtherInfo test && passwd test
```

nicer to use adduser when creating a full user account someone would use regularly instead of just an account for restricting permissions of services, containers, etc. 
