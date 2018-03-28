Webhop - Apache2 + Pagespeed Ansible Role
==========================================

Ansible role to install the latest version of apache2 and the google pagespeed module on an ubuntu-based host.


## Requirements

This role assumes the default site being provisioned is a PHP-based site using the fastcgi module


## Role variables

##### Defaults

- `php_fpm_major_version` - Which PHP FPM version to use (**php5**)
- `apache_force_ssl` - Forces apache to respond with https using `SetEnv https on` (**True**)
- `docroot` - Filesystem path for web assets (**/var/www**)
- `enable_pagespeed` - Enables google pagespeed integration (**false**)
- `enable_mod_status` - Enables apache2 status module and endpoint (**true**)
- `enable_php_fpm_status` - Enables passthrough endpoint for php-fpm status (**true**)
- `mod_status_endpoint` - The URL endpoint to expose apache status (**/server-status**)


Usage
-----

Basic setup:

```yaml
roles:
    - { role: webhop.apache2 }
```

To disable force ssl:

```yaml
roles:
    - { role: webhop.apache2, apache_force_ssl: false }
```

To enable stats endpoint at /apache-stats:

```yaml
roles:
    - { role: webhop.apache2, enable_mod_status: false, mod_status_endpoint: '/apache-stats' }
```

This role will configure Apache to EITHER server HTTP or HTTPS requests, but not both.

In order to configure HTTPS, the following files must exist:

/etc/apache2/ssl/cert.pem
/etc/apache2/ssl/key.pem

Author Information
------------------

* Neil Saunders - neil@beamly.com
* Vik Bhatti - vik@beamly.com
