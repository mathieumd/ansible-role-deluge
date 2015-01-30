Ansible role for Deluge
=========

Install and update [Deluge](http://deluge-torrent.org/).

Loosely based on [jgrowl/ansible-playbook-deluge](https://github.com/jgrowl/ansible-playbook-deluge).

Requirements
------------

This role only works with **Ubuntu** (tested with 14.04) because Debian stable
Wheezy has a [too old
version](https://packages.debian.org/search?searchon=names&keywords=deluge).

Role Variables
--------------

See [defaults](defaults/main.yml):

```yaml
deluge_user: deluge
deluge_group: users

deluge_home: /srv/deluge
deluge_logs: /var/log/deluge

# Shall we enable remote access?
deluge_allow_remote: yes

# Shall we install the Web UI?
deluge_web: no

# http://dev.deluge-torrent.org/wiki/UserGuide/Authentication
# Passwords are saved in "vars/deluge_users/<username>"
deluge_users:
  RemoteUser:
    level: 10
```

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
     - { role: ansible-role-deluge, when: ansible_distribution == 'Ubuntu' }
```

License
-------

GPLv3

