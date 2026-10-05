0: no perms
1: execute
2: write 
4: read

ex:
```
chmod 777 file.txt
```
- gives the owner, group, and other (everyone else) read, write, and execute permissions
- usually a bad idea to give full perms to everyone 

something like below would make more sense
```
chmod 744 file.txt
```
- owner has full perms but group members and other users can only read the file