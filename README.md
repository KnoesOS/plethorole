plethorole
==========

A stockpile of Ansible Roles for use in your Ansible Playbooks.


Version
-------
0.1.1

The Plethorole Project uses Semantic Versioning.


Status
------
Unstable


Tutorial
--------

* Install Ansible >=1.4.
* Create a Roles directory

```
$ mkdir /home/doej/Roles
```

* Update ansible.cfg's 'roles_path' (e.g. '/home/doej/Roles')
* Clone plethorole

```
$ cd /home/doej/Roles
$ git clone git@github.com:KnoesOS/plethorole.git
```

* Use plethorole in your custom Ansible Playbooks.

```
---
# file: rig_acme-web.yml

# Use act_group-by for distro-version matching
- hosts: rig_acme-web  # All distros
  sudo: True
  roles:
    - plethorole/common/act_group-by

# Simple install example
- hosts: rig_acme-web:&Ubuntu-12.04  # Ubuntu 12.04
  sudo: True
  roles:
    - plethorole/ubuntu-12.04/meta_server-base
    - plethorole/ubuntu-12.04/sw_openjdk-7
```

* Use git pull to stay in sync with plethorole-master.

```
$ cd /home/doej/Roles/plethorole
$ git pull
```

* Send pull requests, make suggestions and open issues frequently.


Glossary
------
```
act = an action role
common = a role that applies to multiple contexts
dev = a software role that uses packages from the developer
dev-git = a software role that uses source from the developer's git repo
dev-src = a software role that uses source from the developer
distro = a software role that uses package(s) from the distro
distro-git = a software role that uses source from the distro's git repo
distro-src =  a software role that uses source package(s) from the distro
meta = a role that calls other roles
sw = a role for a software package or software suite
```

Maxims
------
* "meta" roles should be recursively shallow to maintain easy debugging.
