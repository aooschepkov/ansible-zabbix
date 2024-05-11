Ansible Role: Zabbix
=========

An Ansible role that installs Zabbix server and Zabbix agents on your servers. 

Requirements
------------

Ansible

Role Variables
--------------

See `defaults/main.yml`

Dependencies
------------

None

Example Playbook
----------------

```yaml
---
- name: Import zabbix role
  hosts: all
  become: true
  roles:
    - ansible-zabbix
```

Example Inventory
----------------

```ini
[zabbix_server]
zabbix1 ansible_host=192.168.88.223
zabbix2 ansible_host=192.168.88.222
zabbix3 ansible_host=192.168.88.224

[postgres]
zabbix1 ansible_host=192.168.88.223

[zabbix_agent]
alma[1:3]

```

License
-------

BSD

Author Information
------------------
