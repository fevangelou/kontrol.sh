## Using the FTP service

The FTP service as configured in Kontrol is powered by vsftpd and utilizes "virtual" users.

To get started managing FTP users, switch to the main "kontrol" folder:
```
$ cd /root/kontrol
```

For Kontrol 4.x you don't need to switch to any other folder as "kontrol" is now registered as a global command, available anywhere in the system.


### Add an FTP user

For Kontrol 2.x or 3.x:
```
$ ./ftpuser.sh add USERNAME PASSWORD SYSTEM_USER PATH
```

For Kontrol 4.x:
```
$ kontrol ftpuser add USERNAME PASSWORD SYSTEM_USER PATH
```

Adding an FTP user requires a couple extra parameters (beyond their username and password). An FTP user requires an existing system user to be assigned to (one that already has some domain assigned to them) and an absolute path inside the chosen system user.

For example to add user "ftp\_johndoe" with password "abcd1234" under the user "johndoe" and directly pointing to the path "/home/johndoe/domains/some.domain.tld/public\_html/uploads" we would do:

For Kontrol 2.x or 3.x:
```
$ ./ftpuser.sh add ftp_johndoe abcd1234 johndoe /home/johndoe/domains/some.domain.tld/public_html/uploads
```

For Kontrol 4.x:
```
$ kontrol ftpuser add ftp_johndoe abcd1234 johndoe /home/johndoe/domains/some.domain.tld/public_html/uploads
```

### Remove an FTP user
Please note that this process is irreversible and will destroy all user and domain data belonging to that user. Use with caution!

For Kontrol 2.x or 3.x:
```
$ ./ftpuser.sh rem USERNAME
```

For Kontrol 4.x:
```
$ kontrol ftpuser rem USERNAME
```

A 5 second delay gives you time to cancel a request if you change your mind :)

For example to add user ftp_johndoe we would do:

For Kontrol 2.x or 3.x:
```
$ ./ftpuser.sh rem ftp_johndoe
```

For Kontrol 4.x:
```
$ kontrol ftpuser rem ftp_johndoe
```

Pressing Ctrl+C or Cmd+C within 5 seconds will cancel the above action.


### Tips

- Ensure the path this FTP user will be assigned to already exists on the server.
- Deleting an FTP user will NOT delete the actual folder (path) that user was originally assigned to.
- If you make a mistake with the assigned system user or path, simply delete the FTP user you created and just re-create it.
- Prefer to name your ftp user with a "ftp_" prefix as good practice. This will help debugging your system should it ever be compromised as these users will be easy to distinguish in /etc/passwd.
