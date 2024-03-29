
## Changelog

### June 29th - v4.1
* Total overhaul of the command and tools system
* Commands now execute under "kontrol", e.g. "kontrol user add johndoe" or "kontrol domain add johndoe example.com"
* "kontrol" is now a system command and as such can be executed anywhere you are in the system. Instead of cd'ing to the /root/kontrol folder and issuing direct script commands, e.g. ./domain.sh ..., you now simply replace all such script commands with "kontrol domain ..." or "kontrol user ..." and so on, executable anywhere in the system.
* "kontrol user add" command will now auto-generate a password for the user and also create an associated database user with an auto-generated password as well
* New installers added
* New common configurations for WordPress and Drupal added in Nginx
* Improvements on existing installers

### December 20th, 2021 - v3.7
* Make symlink of kontrol.sh to /usr/local/sbin/ and stop using `alias kontrol='/root/kontrol/kontrol.sh'`

### December 16th, 2021 - v3.6
* From this version on, all new releases will be updated with a changelog list
* Added support for EL8, removed common package installing from main installers (either Ubuntu or EL), updated cPanel installer for EL8

### December 15th, 2021 - v3.5
* Added support for PHP up to v8.1
* Includes phpMyAdmin v5.1.1 (latest)
* Updated my.cnf for up to MySQL 8
* Added support for Varnish v7
* Added support for FTP (based on vsftpd and utilizing "virtual" users)
* Updated all external utilities (e.g. Tuning Primer, MySQL Tuner etc.)
* Updated the LetsEncrypt certificate issuing script

### December 18th, 2020 - v3.0
* First new version in 2 years.
* New unified web control panel with a single secure login for all apps except phpMyAdmin (for precaution & additional security).
* Many under-the-hood improvements, especially in how Nginx and Varnish interface and under heavy caching scenarios. Nginx can easily be used for HTTPS termination, proxying requests to Varnish which in turn fetches content from Nginx on port 8080.
* Nginx caching has been improved with on-demand and fixed caching strategies, configurable per vhost.
* Added LetsEncrypt script (based off "certbot") to easily issue & renew certificates for a server's hostname and associated domains.
* Supports PHP versions 5.6 to 7.4.
* Supports MySQL versions 5.7 & 8.0, including new optimized my.cnf setup for both versions.
* Added support for Ubuntu 20.04 LTS (latest).
* Uses latest updates on all 3rd party components and scripts.
