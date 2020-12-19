
## Changelog

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
