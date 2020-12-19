## Managing Services

### Varnish
Use the Varnish specific script in "/root/kontrol" to enable or disable the Varnish service.

Varnish will probably be disabled by default.

Switch to the main Kontrol folder first:
```
$ cd /root/kontrol
```

**To enable Varnish**
```
$ ./varnish.sh on
```

**To disable Varnish**
```
$ ./varnish.sh off
```

You don't need to restart Nginx or PHP-FPM after switching Varnish on or off.



### LetsEncrypt
At least the server's hostname has to be valid and point back to the server's IP so that LetsEncrypt can issue a certificate for Kontrol's web UI.

Anytime a new domain is added, you can simply execute the LetsEncrypt script like this:

```
$ /root/kontrol/tools/letsencrypt.sh
```

The process will also copy the hostname's (valid) certificate to be used by the firewall's UI as well (CSF).
