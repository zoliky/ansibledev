Audacity
========

Ansible role for installing Audacity.

Requirements
------------

- Ansible 2.14 or later.

Role variables
--------------

| ansible_distribution | ansible_os_family |
| -------------------- | ----------------- |
| Debian               | Debian            |
| Linux Mint           | Debian            |
| openSUSE Leap        | Suse              |
| Fedora               | RedHat            |

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