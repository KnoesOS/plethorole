plethorole
==========

A diverse stockpile of reusable Ansible roles.


Version
-------
0.1.4

The Plethorole Project uses Semantic Versioning.


Status
------
Unstable


Tutorial
--------

* Install Ansible >=1.4.
* Create a Roles directory

```
$ mkdir /home/bob/Roles
```

* Update ansible.cfg's 'roles_path' (e.g. '/home/bob/Roles')
* Clone plethorole

```
$ cd /home/bob/Roles
$ git clone git@github.com:KnoesOS/plethorole.git
```

* Use plethorole in your custom Ansible Playbooks.

```
---
# file: group_database.yml

# Initialize Plethorole
- hosts: group_database
  sudo: True
  roles:
    - plethorole/v1/init
 
# Core Servers: Ubuntu-12.04-x86_64
- hosts: group_core:&dist_Ubuntu:&distvers_12.04:&distarch_x86_64
  sudo: True
  roles:
    - plethorole/v1/dyn_debuntu/dist_ubuntu/v_12.04/arch_x64/meta_base/ori_def/v_def/arch_def/twst_def/install
    - plethorole/v1/dyn_debuntu/dist_ubuntu/v_12.04/arch_x64/meta_core/ori_def/v_def/arch_def/twst_def/install
```

* Use git pull to stay in sync with plethorole-master.

```
$ cd /home/bob/Roles/plethorole
$ git pull
```

* Send pull requests, make suggestions and open issues frequently.


Glossary
------
```
common = a role that applies to multiple contexts
meta = a role that calls other roles
```

Maxims
------
* "meta" roles shall always be recursively shallow for easy debugging.
