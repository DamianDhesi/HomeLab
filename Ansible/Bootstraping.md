Need to install ansible-core (includes python3) and git 

then, to set up cron job run using bootstrap playbook
```
ansible-pull -U https://github.com/DamianDhesi/ansible_config.git -C main bootstrap.yml
```

for bootstrapping on PVE hosts use
```
ansible-pull -U https://github.com/DamianDhesi/ansible_config.git -C main bootstrap-host.yml
```

for bootstrapping on VM with docker use
```
ansible-pull -U https://github.com/DamianDhesi/ansible_config.git -C main bootstrap-docker.yml
```
