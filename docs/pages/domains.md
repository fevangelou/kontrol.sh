## Managing Domains

To manage domains in a server powered by Kontrol, you can utilize the "kontrol domain" command.

It's important that you have first created regular users to whom you can then assign (or unassign) domains.


### To add a domain to an existing user

```
$ kontrol domain add USERNAME NAKED_DOMAIN_OR_SUBDOMAIN
```

For example, to add the domain example.com to user johndoe, you would do:

```
$ kontrol domain add johndoe example.com
```

When you add a naked domain, Kontrol will automatically create a "www." subdomain as well.


### To remove a domain from an existing user

```
$ kontrol domain rem johndoe example.com
```

For example, to remove the domain example.com from user johndoe, you would do:

```
$ kontrol domain rem johndoe example.com
```

This action will delete the entire domain folder at: */home/johndoe/domains/example.com/*


### To switch PHP version for a certain domain

When adding a new domain, the default PHP version set in kontrol.conf will take effect by default for new domains.

To switch that domain or any domain at any point to a different PHP version, simply use the following command:

```
$ kontrol domain switch USERNAME NAKED_DOMAIN_OR_SUBDOMAIN TARGET_PHP_VERSION
```

Valid values for TARGET\_PHP\_VERSION at the time of writing are: 5.6, 7.4 and 8.1 up to 8.4

For example, to switch domain "example.com" (assigned to user "johndoe") to PHP 8.4, you would just do:

```
$ kontrol domain switch johndoe example.com 8.4
```
