Webhop - Apache2 + Pagespeed Ansible Role
==========================================

Ansible role to install the latest version of apache2 and the google pagespeed module on an ubuntu-based host.


## Requirements

This role assumes the default site being provisioned is a PHP-based site using the fastcgi module


## Role variables

##### Defaults

- `apache_force_ssl` - Forces apache to respond with https using `SetEnv https on` (**True**)


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


This role will configure Apache to EITHER server HTTP or HTTPS requests, but not both.

In order to configure HTTPS, the following files must exist:

/etc/apache2/ssl/cert.pem
/etc/apache2/ssl/key.pem

Author Information
------------------

* Neil Saunders - neil@beamly.com
