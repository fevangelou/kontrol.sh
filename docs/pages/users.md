## Managing Users

Before adding new domains in a server powered by Kontrol, you must add regular users utilizing the "user.sh" script in the folder "/root/kontrol".

For Kontrol 2.x or 3.x:

Switch to the main "kontrol" folder:
```
$ cd /root/kontrol
```

For Kontrol 4.x you don't need to switch to any other folder as "kontrol" is now registered as a global command, available anywhere in the system.


### To add a user

For Kontrol 2.x or 3.x:
```
$ ./user.sh add USERNAME PASSWORD
```

For Kontrol 4.x:
```
$ kontrol user add USERNAME
```
...the password is auto-generated and a database user is also created with a different auto-generated password as well. Passing a password after the username will enforce a custom password and not an auto-generated one.

For example to add user johndoe with password abcd1234 we would do:

For Kontrol 2.x or 3.x:
```
$ ./user.sh add johndoe abcd1234
```

For Kontrol 4.x, assuming we don't care about setting a specific password, we can opt-in for a simpler command with an auto-generated 16-character password:
```
$ kontrol user add johndoe
```


### To remove a user
Please note that this process is irreversible and will destroy all user and domain data belonging to that user. Use with caution!

For Kontrol 2.x or 3.x:
```
$ ./user.sh rem USERNAME
```

For Kontrol 4.x
```
$ kontrol user rem USERNAME
```

A 5 second delay gives you time to cancel a request if you change your mind :)

For example to add user johndoe we would do:

For Kontrol 2.x or 3.x:
```
$ ./user.sh rem johndoe
```

For Kontrol 4.x
```
$ kontrol user rem johndoe
```
If there is a corresponding "johndoe" database user, it will also be deleted. However Kontrol will NEVER delete a database. This process will always be manual to avoid accidental data loss.

Pressing Ctrl+C within 5 seconds will cancel the above action.


### Tips

- Avoid creating or deleting system users with the use of useradd or userdel which are native Linux commands.
- In Kontrol version 2.x & 3.x creating or deleting system users does not have any effect on database users, which are to be entirely managed by phpMyAdmin (or MySQL CLI commands).
