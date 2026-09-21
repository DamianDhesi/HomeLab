run all commands on host
```
connection: local
```

run commands as root
```
become: true
```

can run tasks [asynchronously](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_async.html)
- async
	- time in seconds to wait before canceling task
- poll
	- number of times to poll
	- If 0, then its set to fire-and-forget, so the playbook will continue to the next task
## Modules
[ansible builtin commands for apt](https://docs.ansible.com/projects/ansible/latest/collections/ansible/builtin/apt_module.html)

can run commands in shell with [builtin shell module](https://docs.ansible.com/projects/ansible/latest/collections/ansible/builtin/shell_module.html)



