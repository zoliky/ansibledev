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

Suppose we're setting up ten different Linux distributions. Nine of them refer to the spell check package as `hunspell`. However, Mageia Linux calls it `hunspell-us`. To address this difference, we create a new file named `mageia.yml` in the `vars` folder. Inside this file, we define a custom variable called `package_name` and set it to `hunspell-us`. This variable takes precedence over the default value defined in the `defaults` folder specifically for Mageia Linux, while retaining the default value for all other distributions.


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
