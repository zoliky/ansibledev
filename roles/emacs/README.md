Emacs
=====

Ansible role for installing Emacs.

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
    - ansible.builtin.include_role: emacs
```

License
-------

BSD

Author Information
------------------

Zoltan Kiraly &lt;zoltan.git@fastmail.com&gt;