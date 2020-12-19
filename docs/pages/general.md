## General How-To

Explore the options in the main "kontrol" script after installation with:

```
$ kontrol -h
```

At the time of writing, this would be output from the command above:

```
Kontrol is a handy suite of scripts for deploying and managing Ubuntu & CentOS servers.

Current version: 3.0
Released: December 18th, 2020

Usage: kontrol [command]

Pre-deployment commands:
    pre              Install required server software (usually upon initial server deployment)
    lcl              Fix the server locale (usually in OpenVZ or LXC based VMs) [Ubuntu only]

Main commands:
    (empty)          Restart main web services only (PHP5-FPM, Apache and/or Nginx, Varnish)
    all              Restart Cron, CSF & LFD (if installed), Munin (if installed),
                     MySQL, PHP5-FPM, Apache, Nginx, Varnish
    upd              Update server software

Database related commands:
    tp               Run Tuning Primer diagnostics for MySQL (up to v5.6)
    tp2              Run Tuning Primer (by RootService) diagnostics for MySQL (up to v5.7)
    mt               Run MySQL Tuner diagnostics for MySQL
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
