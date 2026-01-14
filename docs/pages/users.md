## Managing Users

Before adding new domains in a server powered by Kontrol, you must add regular users first.


### To add a user

```
$ kontrol user add USERNAME
```

The password is auto-generated and a database user is also created with a different auto-generated password as well. Passing a password after the username will enforce a custom password and not an auto-generated one.

For example to add user johndoe (in the system and database) with separate secure auto-generated 16-character passwords:

```
$ kontrol user add johndoe
```


### To remove a user
Please note that this process is irreversible and will destroy all user and domain data belonging to that user. Use with caution!

```
$ kontrol user rem USERNAME
```

A 5 second delay gives you time to cancel a request if you change your mind :)

For example to remove user johndoe we would do:

```
$ kontrol user rem johndoe
```

If there is a corresponding "johndoe" database user, it will also be deleted. However Kontrol will NEVER delete a database. This process will always be manual to avoid accidental data loss.

Pressing Ctrl+C within 5 seconds will cancel the above action.


### Tips

- Avoid creating or deleting system users with the use of useradd or userdel which are native Linux commands.
