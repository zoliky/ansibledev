GNOME
=====

Ansible role for installing and configuring the GNOME desktop environment.

Requirements
------------

- Ansible 2.14 or later.

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
    - ansible.builtin.include_role: gnome
```

License
-------

BSD

Author Information
------------------

Zoltan Kiraly &lt;zoltan.git@fastmail.com&gt;