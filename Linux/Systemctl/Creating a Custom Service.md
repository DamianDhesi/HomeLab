administrator configured service files are held in /etc/systemd/system
- location for custom services 
	- custom services are nice when there is an executable/command that you want to run automatically during boot process
- requires sudo/su permissions

can create a new service by making a new .service file
```
nano /etc/systemd/system/<service_name>.service
```

## Writing a service file
[broken into Unit, Service, and Install sections](https://docs.redhat.com/en/documentation/red_hat_enterprise_linux/9/html/using_systemd_unit_files_to_customize_and_optimize_your_system/assembly_working-with-systemd-unit-files_working-with-systemd)
### Unit
- Description
	- provides a description of the service
- Documentation
	- provides URIs refering to documenation
- After
	- starts the service after some condition
		- network.target is a common condition indicating that the script should run after network capabilities become active during boot process 
- Requires
	- configures dependencies on other services 
	- service won't activate if dependent services fail to start
- Wants
	- weaker dependencies 
	- any services listed won't impact whether the service will start or not

ex:
```
[Unit]
Description=An example service
After=network.target
```
### Service
 - Type
	 - configures the startup type
		 - simple
			 - default
			 - process created with ExecStart is the main process
		 - forking
			 - process created with ExecStart spawns a child process with child becoming the main process and the parent exiting
		 - oneshot
			 - process exists before starting other dependent services
		 - dbus
			 - other dependent services are started only after the process gains a d-bus name
		 - notify
			 - other dependent services are started only after notification message sent via sd_notify()
		 - idle
			 - service is delayed until all jobs are finished
 - ExecStart
	 - commands or scripts to be executed when service starts
 - ExecStop
	 - commands or scripts that execute when service stops
 - ExecReload
	 - commands or scripts that execute on service restart/reload
 - Restart
	 - if set, service will restart after its process exits
		 - there is an execption if clean stop via systemctl command is done
 - RestartSec
	 - seconds to wait before restarting
 - RemainAfterExit
	 - if set to true, service is considered active even when all processes exited 
 - User
	 - user perms that the process will have
 - Group
	 - group perms that the process will have
 - Environment
	 - any environmental variables that need to be set for the process to properly run

ex:
```
[Service]
Restart=always
RestartSec=5
Type=simple
User=exUser
Group=exGroup
Environment="ExVar=example_value"
WorkingDirectory=path/to/desired/working/directory
ExecStart=path/to/executable/script
```
- important that the user and group assigned to the service has the permissions to execute the desired script/command
- generally better to give an executable script to ExecStart so that the service can be edited via changing the script instead of the .service file it self
### Install
- Alias
	- space separated list of other names for service
- Requiredby
	- list of services that depend on this service
	- dependent services gain a Requires dependency with this service
- WantedBy
	- list of services that depend weakly on this service
	- get a Want dependency with this service
- Also
	- specifies a list of units to be installed or uninstalled along with the unit

ex:
```
[Install]
WantedBy=multi-user.target
```
- [.target files refer to a grouping of services and sockets](https://unix.stackexchange.com/questions/159462/what-is-systemds-target-service-and-socket/159488#159488) (daemons that only run when a connection is made to a specific ip and port)
	- most services/sockets are under multi-user.target

## Starting a Custom Service
interacting with services will typically require sudo/su permissions with the exception of checking service status

when adding/changing servcies it is important to reload systemctl so changes take effect
```
systemctl reload-daemon
```

enable desired service
- must be done when creating a new service
```
systemctl enable <service_name>.service
```
can also disable an existing service if desired
```
systemctl disable <service_name>.service
```

start a service
```
systemctl start <service_name>
```

restart a service
```
systemctl restart <service_name>
```

stop a service
```
systemctl stop <service_name>
```

check service status
- will show if it is active or not and an exit code if it did exit
- service related output will also be shown
```
systemctl status <service_name>
```