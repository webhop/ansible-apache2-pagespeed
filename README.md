Webhop - Apache2 + Pagespeed Ansible Role
==========================================

Ansible role to install the latest version of apache2 and the google pagespeed module on an ubuntu-based host.


## Requirements

This role assumes the default site being provisioned is a PHP-based site using the fastcgi module


Usage
-----

```yaml
roles:
    - { role: webhop.apache2 }
```

Author Information
------------------

* Neil Saunders - neil@beamly.com
