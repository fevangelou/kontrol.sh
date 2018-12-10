## Managing Domains

To manage domains in a server powered by Kontrol, you can utilize the "domain.sh" script in the folder "/root/kontrol".

It's important that you have first created regular users to whom you can then assign (or unassign) domains.

Switch to the main "kontrol" folder:
```
$ cd /root/kontrol
```

### To add a domain to an existing user
```
$ ./domain.sh add USERNAME NAKED_DOMAIN_OR_SUBDOMAIN
```

For example, to add the domain example.com to user johndoe, you would do:
```
$ ./domain.sh add johndoe example.com
```

When you add a naked domain, Kontrol will automatically create a "www." subdomain as well.

### To remove a domain from an existing user
```
$ ./domain.sh rem USERNAME NAKED_DOMAIN_OR_SUBDOMAIN
```

For example, to remove the domain example.com from user johndoe, you would do:
```
$ ./domain.sh rem johndoe example.com
```

This action will delete the entire domain folder at: */home/johndoe/domains/example.com/*


### To switch PHP version for a certain domain
When adding a new domain, the default PHP version set for new domains in /root/kontrol/kontrol.conf will take effect by default.

To switch that domain or any domain at any point to a different PHP version, simply use the following command:
```
$ ./domain.sh switch USERNAME NAKED_DOMAIN_OR_SUBDOMAIN TARGET_PHP_VERSION
```

Valid values for TARGET\_PHP\_VERSION at the time of writing are: 5.6, 7.0, 7.1 & 7.2

For example, to switch domain example.com from user johndoe to PHP 7.2, you would do:
```
$ ./domain.sh switch johndoe example.com 7.2
```
