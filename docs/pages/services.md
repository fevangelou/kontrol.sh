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
