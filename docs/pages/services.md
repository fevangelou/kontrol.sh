## Managing Services

### Varnish
Use the Varnish specific command to enable or disable the Varnish service.

**To enable Varnish**

```
$ kontrol varnish on
```

**To disable Varnish**

```
$ kontrol varnish off
```

You don't need to restart Nginx or PHP-FPM after switching Varnish on or off.


### LetsEncrypt or ZeroSSL
At least the server's hostname has to be valid and point back to the server's IP so that LetsEncrypt or ZeroSSL can issue a certificate for Kontrol's web UI.

Anytime a new domain is added, you can simply execute the SSL issuing script like this:

```
$ kontrol ssl
```

The process will also symlink the hostname's (valid) certificate to be used by the firewall's UI as well (CSF).

To add an SSL certificate for a specific domain simply do:

```
$ kontrol ssl example.com www.example.com
```

(this will ensure both the naked and "wwww" subdomain get a valid SSL certificate)
