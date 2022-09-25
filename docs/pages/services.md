## Managing Services

### Varnish
Use the Varnish specific script in "/root/kontrol" to enable or disable the Varnish service.

Varnish will probably be disabled by default.

Switch to the main Kontrol folder first:
```
$ cd /root/kontrol
```

For Kontrol 4.x you don't need to switch to any other folder as "kontrol" is now registered as a global command, available anywhere in the system.


**To enable Varnish**

For Kontrol 2.x or 3.x:
```
$ ./varnish.sh on
```

For Kontrol 4.x:
```
$ kontrol varnish on
```

**To disable Varnish**
For Kontrol 2.x or 3.x:
```
$ ./varnish.sh off
```

For Kontrol 4.x:
```
$ kontrol varnish off
```

You don't need to restart Nginx or PHP-FPM after switching Varnish on or off.



### LetsEncrypt
At least the server's hostname has to be valid and point back to the server's IP so that LetsEncrypt can issue a certificate for Kontrol's web UI.

Anytime a new domain is added, you can simply execute the LetsEncrypt script like this:

```
$ /root/kontrol/tools/letsencrypt.sh
```

The process will also symlink the hostname's (valid) certificate to be used by the firewall's UI as well (CSF).
