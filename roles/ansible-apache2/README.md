Role Name
=========

An [Ansible] role to install [Apache]

Requirements
------------

None

Role Variables
--------------

```
---
# defaults file for ansible-apache2

# Defines if Apache2 should be configured
apache2_config: false

# Defines if php.ini should be configured for Apache2
apache2_config_php: false

# Defines if Apache2 virtual hosts should be configured
apache2_config_virtual_hosts: false

# Defines Apache2 default listen port
apache2_default_port: 80

# Defines if php-sqlite should be installed
apache2_install_php_sqlite: false

# Defines if php should be installed
apache2_install_php: false

# Defines max memory for Apache php
# default is 128M
apache2_php_max_memory: '128M'

apache2_server_admin: 'webmaster@localhost'

# Define Apache2 virtual hosts
apache2_virtual_hosts:
  - documentroot: '/var/www/example.com'
    default_site: false
    port: 80
    serveradmin: '{{ apache2_server_admin }}'
    servername: 'www.example.com'
  - documentroot: '/var/www/example.org'
    default_site: false
    port: 80
    serveradmin: '{{ apache2_server_admin }}'
    servername: 'www.example.org'
  - documentroot: '/var/www/html'
    default_site: true
    port: 80
    serveradmin: '{{ apache2_server_admin }}'
    servername: ''
```

Dependencies
------------

None

Example Playbook
----------------

```
- hosts: apache_servers
  become: true
  vars:
  roles:
    - role: ansible-apache2
  tasks:
```

License
-------

BSD

Author Information
------------------

Larry Smith Jr.
- @mrlesmithjr
- http://everythingshouldbevirtual.com
- mrlesmithjr [at] gmail.com

[Ansible]: <https://www.ansible.com>
[Apache]: <http://httpd.apache.org/>
