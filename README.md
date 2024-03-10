IT Automation Project
=====================

About
-----

Work in progress.

```
$ ansible-playbook workstation.yml -e "target=workstation"
$ ansible-pull -U https://github.com/zoliky/ansibledev.git -C main
```

 
**Module currently under development:**

**`roles/chrome`:**
 
| Distribution             | Status           |
|--------------------------|------------------|
| Debian 12 Bookworm       | DONE             |
| Fedora 39                | DONE             |
| Linux Mint 21.3 Virginia | Work in progress. Error: Could not get lock /var/lib/apt/lists/lock |
| Linux Debian Edition     | Work in progress |
| openSUSE Leap 15.5       | Work in progress. Error: Could not resolve module zypper_repository |
| openSUSE Tumbleweed      | Work in progress |
| Red Hat Enterprise Linux | Work in progress |
| Ubuntu Linux             | Work in progress |
| Manjaro Linux            | Work in progress |
| MX Linux                 | Work in progress |


Requirements
------------

- Ansible 2.14 or later
- Git

Dependencies
------------

No dependencies.

Group variables
---------------

This folder allows groups to be defined to provision computers with different sets of packages and configurations based on user needs. The `workstation` serves as a foundational group, containing packages and configurations provisioned for every user. All other groups inherit from `workstation` and may add additional modules as necessary.

Host variables
--------------

Role variables
--------------

The `defaults` folder in each role contains default variables that users should NOT change. On the other hand, the `vars` folder holds variables intended for user modification, which override the ones in `defaults`. In simpler terms, the `vars` folder takes precedence over `defaults`.

Example Playbook
----------------

```
---
- name: Setup a workstation
  hosts: "{{ target }}"
  connection: local # we're debugging, so the hosts may not exist

  tasks:
    - name: Include roles
      ansible.builtin.include_role:
        name: "{{ item }}"
      loop: "{{ workstation_roles }}"
```

License
-------

BSD

Author Information
------------------

Zoltan Kiraly &lt;zoltan.git@fastmail.com&gt;
