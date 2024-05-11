Ansible Role: Zabbix
=========

An Ansible role that installs containerized Zabbix server and Zabbix agents on your <ins>systemd enabled</ins> linux servers.
 - Supports HA mode for server and UI. (HA DB will be added in the future)
 - HA mode is enabled by default if there are more than 1 host in `zabbix_server` inventory group.

Requirements
------------

Ansible

Role Variables
--------------

See `defaults/main.yml`

If using Zabbix in HA mode, pay attention to `keepalived_virtual_ipaddress` variable. This is a VIP (Virual IP Address) that shouln't be in use within your network.

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
