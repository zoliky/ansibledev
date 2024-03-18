Audacity
========

Ansible role for installing Audacity.

Requirements
------------

- Ansible 2.14 or later.

This role was tested on:

- FreeBSD 14
- Fedora 39
- Archlinux 2024.03.01
- Debian 12, 13-Trixie (Testing)
- openSUSE Leap 15.5, Tumbleweed

Role variables
--------------

Dependencies
------------

No dependencies.

Example Playbook
----------------

```
---
- hosts: localhost  
  tasks:
    - ansible.builtin.include_role: audacity
```

License
-------

BSD

Author Information
------------------

Zoltan Kiraly &lt;zoltan.git@fastmail.com&gt;