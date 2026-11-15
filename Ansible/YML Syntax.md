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

## Scalars
folded block scalars fold lines into a single line with a space in between. Empty lines will count as newlines
```
# Source - https://stackoverflow.com/a/72084881
# Posted by flyx
# Retrieved 2026-11-13, License - CC BY-SA 4.0

a: > # folds into "one two\nthree four\n\nfive\n"
  one
  two

  three
  four


  five
```

literal block scalars don't do line folding
```
a: |
	one
	two 
	three
# foldes into one\ntwo\nthree\n
```

Adding a - to > and | will get rid of the trailing new line at the end
- written as >- and |-
```
# Source - https://stackoverflow.com/a/72084881
# Posted by flyx
# Retrieved 2026-11-13, License - CC BY-SA 4.0

a: >- # folded into "one two"
  one
  two
b: >- # folded into "one\ntwo"
  one

  two
```
