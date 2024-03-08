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
