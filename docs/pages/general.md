## General How-To

Explore the options in the main "kontrol" script after installation with:

```
$ kontrol -h
```

At the time of writing, this would be output from the command above:

```
 __ __            __             __
   / //_/___  ____  / /__________  / /
  / ,< / __ \/ __ \/ __/ ___/ __ \/ /
 / /| / /_/ / / / / /_/ /  / /_/ / /
/_/ |_\____/_/ /_/\__/_/   \____/_/

        https://kontrol.sh

Kontrol is a handy suite of scripts for deploying and managing Ubuntu & CentOS servers.

Current version: 4.12
Released: January 16th, 2026

Usage: kontrol [command]

~ Pre-deployment commands:
    pre             Install required server software (usually upon initial server deployment)
    lcl             Fix the server locale (usually in OpenVZ or LXC based VMs & EL variants)

~ Service Commands:
    (empty)         Restart main web services only (PHP-FPM, Apache and/or Nginx, Varnish)
    all             Restart Cron, CSF & LFD (if installed), Munin (if installed),
                    MySQL, PHP-FPM (all versions), Apache, Nginx, Varnish
    upd             Update server software
    info            Show basic system information

~ Database Utilities:
    tp              Run Tuning Primer diagnostics for MySQL or MariaDB
    mt              Run MySQL Tuner diagnostics for MySQL or MariaDB
    mf              Run MySQL Fragmentation Finder (and Fixer) to optimize all server databases

~ Service Checks:
    check nginx     Check if the Nginx configuration is valid
    check varnish   Check if the Varnish configuration is valid
    keys            Renew expired software keys

~ Network Utilities:
    ip              Display server's main IP
    80              Show active connections on port 80 sorted by connection count & IP,
                    including total concurrent connections count
    443             Show active connections on port 443 sorted by connection count & IP,
                    including total concurrent connections count
    80-443          Show totals for concurrent connections on ports 80 & 443
        ip2isp          List the top 30 IPs by request count along with their ISP name - this
                        must be run inside the /home/USERNAME/domains/DOMAIN/logs folder of any given
                                        domain to work properly.

~ Filesystem Utilities:
    fixownerperms (or fop)   Fix owner permissions in all user /public_html directories
    fixaccessperms (or fap)  Change file & directory access permissions to 644 & 755 respectively
                             in all user /public_html directories
    cleanup                  Cleanup Mac or Windows specific metadata & Apache error_log files
                             in all user /public_html directories
        hh                       Cleanup and overwrite bash history file for enhanced privacy

~ SSL Certificates:
    ssl             Issue certificates through LetsEncrypt, ZeroSSL or other CAs

~ Purge Caches:
    purgecache      Purge Nginx's "cache" & "temp" folders,
                    then restart Apache and/or Nginx

~ Fun Utilities:
    w (or weather)  Show the current weather forecast - add 3-letter airport code for
                    exact weather forecast (e.g. muc, ath etc.)

~ Help:
    -h OR --help    Show this help page


~~ Enjoy Kontrol! ~~



~ Powered by Kontrol v4.12 ~

```

As noted above, you can perform basic tasks like:

1. Upgrade the system
```
$ kontrol upd
```

2. Restart basic or all services:
```
$ kontrol
```
and
```
$ kontrol all
```

3. Defragment/optimize all databases:
```
$ kontrol mf
```
