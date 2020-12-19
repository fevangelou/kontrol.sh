## Managing Users

Before adding new domains in a server powered by Kontrol, you must add regular users utilizing the "user.sh" script in the folder "/root/kontrol".

Switch to the main "kontrol" folder:
```
$ cd /root/kontrol
```

### To add a user
```
$ ./user.sh add USERNAME PASSWORD
```

For example to add user johndoe with password abcd1234 we would do:
```
$ ./user.sh add johndoe abcd1234
```


### To remove a user
Please note that this process is irreversible and will destroy all user and domain data belonging to that user. Use with caution!

```
$ ./user.sh rem USERNAME
```

A 5 second delay gives you time to cancel a request if you change your mind :)

For example to add user johndoe we would do:
```
$ ./user.sh rem johndoe
```

Pressing Ctrl+C within 5 seconds will cancel the above action.



### Tips

- Avoid creating or deleting system users with the use of useradd or userdel which are native Linux commands.
- Creating or deleting system users does not have any effect on database users, which are to be entirely managed by phpMyAdmin (or MySQL CLI commands).
