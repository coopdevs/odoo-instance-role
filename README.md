Odoo instance role
=========

This role will install and setup the following components:

 - PostgreSQL
 - Nginx
 - Let's Encrypt SSL certificate (with Nginx plugin)
 - Odoo ERP

Role Variables
--------------

```
odoo_instance_odoo_user: odoo
odoo_instance_database_name: odoo

odoo_instance_certificate_authority_email: # Email address to manage SSL certificate (No default)
odoo_instance_odoo_admin_password: # Odoo master password (No default)

odoo_instance_odoo_version: # odoo-role has a default version
odoo_instance_odoo_release: # odoo-role has a default release
```

Dependencies
------------

- [coopdevs.sys-admins-role](https://galaxy.ansible.com/coopdevs/sys-admins-role/)
- [geerlingguy.postgresql](https://galaxy.ansible.com/geerlingguy/postgresql/)
- [geerlingguy.security](https://galaxy.ansible.com/geerlingguy/security/)
- [jdauphant.nginx](https://galaxy.ansible.com/jdauphant/nginx/)
- [coopdevs.certbot_nginx](https://galaxy.ansible.com/coopdevs/certbot_nginx/)
- [coopdevs.odoo-role](https://galaxy.ansible.com/coopdevs/odoo-role/)

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
     - role: coopdevs.odoo-instance-role
       vars:
         odoo_instance_odoo_user: odoo
         odoo_instance_database_name: odoo
         odoo_instance_certificate_authority_email: info@coopdevs.org
         odoo_instance_odoo_admin_password: 1234!?
```

License
-------

GPLv3

Author Information
------------------

http://coopdevs.org
