TeXLive
=======

Ansible role for installing TexLive.

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
    - ansible.builtin.include_role: texlive
```

License
-------

BSD

Author Information
------------------

Zoltan Kiraly &lt;zoltan.git@fastmail.com&gt;