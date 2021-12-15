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

Current version: 3.5
Released: December 15th, 2021

Usage: kontrol [command]

Pre-deployment commands:
    pre              Install required server software (usually upon initial server deployment)
    lcl              Fix the server locale (usually in OpenVZ or LXC based VMs) [Ubuntu only]

Main commands:
    (empty)          Restart main web services only (PHP5-FPM, Apache and/or Nginx, Varnish)
    all              Restart Cron, CSF & LFD (if installed), Munin (if installed),
                     MySQL, PHP-FPM (all versions), Apache, Nginx, Varnish
    upd              Update server software

Database related commands:
    tp               Run Tuning Primer diagnostics for MySQL (up to v8) or MariaDB
    mt               Run MySQL Tuner diagnostics for MySQL (up to v8) or MariaDB
    mf               Run MySQL Fragmentation Finder (and Fixer) to optimize all server databases

Service related commands:
    check nginx      Check if the Nginx configuration is valid
    check varnish    Check if the Varnish configuration is valid

Utility commands:
    80               Show active connections on port 80 sorted by connection count & IP,
                     including total concurrent connections count
    443              Show active connections on port 443 sorted by connection count & IP,
                     including total concurrent connections count
    fixaccessperms   Change file & directory access permissions to 644 & 755 respectively
                     in all user /public_html directories
    fixownerperms    Fix owner permissions in all user /public_html directories
    cleanup          Cleanup Mac or Windows specific metadata & Apache error_log files
                     in all user /public_html directories
    purgecache       Purge Nginx's "cache" & "temp" folders,
                     then restart both Apache & Nginx
    keys             Renew expired software keys
    history          Cleanup user history
    ip               Display server's main IP
    info             Show basic system info
    -h OR --help     Show this info page

~~ Enjoy Kontrol! ~~


=== Powered by Kontrol v3.5 ===
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
