plethorole
==========

A stockpile of Ansible Roles for use in your Ansible Playbooks...


Version
-------
0.1.0

The Plethorole Project uses Semantic Versioning.


Status
------
Unstable


Tutorial
--------
1. Install Ansible >=1.4.
2. Create a Roles directory
```
$ mkdir /home/doej/Roles
```
3. Update ansible.cfg's 'roles_path' (e.g. '/home/doej/Roles')
4. Clone plethorole
```
$ cd /home/doej/Roles
$ git clone git@github.com:KnoesOS/plethorole.git
```
5. Use plethorole in your custom Ansible Playbooks.
```
---
# file: rig_acme-web.yml

# Use act_group-by for distro-version matching
- hosts: rig_acme-web  # All distros
  sudo: True
  roles:
    - plethorole/common/act_group-by

# Simply install OpenJDK-7 w/JAVA_HOME
- hosts: rig_acme-web:&Ubuntu-12.04  # Ubuntu 12.04
  sudo: True
  roles:
    - plethorole/ubuntu-12.04/sw_openjdk-7
```
6. Use git pull to stay in sync with plethorole-master.
```
$ cd /home/doej/Roles/plethorole
$ git pull
```
7. Send pull requests and open issues as desired.
