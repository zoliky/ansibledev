Ansible Development Repository
==============================

About
-----

Work in progrss

```
$ ansible-playbook workstation.yml -e "target=workstation"
$ ansible-pull -U https://github.com/zoliky/ansibledev.git -C main
```

Requirements
------------

- Ansible 2.14 or later.

Dependencies
------------

No dependencies.

Group variables
---------------

This folder allows groups to be defined to provision computers with different sets of packages and configurations based on user needs. The `workstation` serves as a foundational group, containing packages and configurations provisioned for every user. All other groups inherit from `workstation` and may add additional modules as necessary.

Example:

John is a developer and he's in the `workstation_developer` group. Sarah wants lots of board and puzzle games, so she's in the `workstation_gaming` group. Zoltan loves using Emacs and needs LaTeX, which is really big (8GB), so he's in the `workstation_editing` group. John and Sarah don't want such a big thing. John and Sarah prefer not to have such large software installed and configured on their machines.


Host variables
--------------

Role variables
--------------

The `defaults` folder in each role contains default variables that users should NOT change. On the other hand, the `vars` folder holds variables intended for user modification, which override the ones in `defaults`. In simpler terms, the `vars` folder takes precedence over `defaults`.

Example:

Imagine we're setting up ten different Linux distributions. While nine of them refer to the spell check package as `hunspell`, Mageia Linux uses `hunspell-us`. To handle this difference, we create a new file named `mageia.yml` in the `vars` folder. Inside, we define a custom variable `package_name` as `hunspell-us`. Ansible will prioritize this variable over the one defined in the `defaults` folder specifically for Mageia Linux, while retaining the default value for all other Linux distributions.

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
