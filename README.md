ansible-shell-users
===================

This role manage shell users

[![Ansible Galaxy](https://img.shields.io/ansible/role/15682.svg)](https://galaxy.ansible.com/salamachinas/shell-users/)

Requirements
------------

This role requires Ansible 2.0 or higher and platform requirements are listed
in the metadata file.

Install
-------

```sh
ansible-galaxy install salamachinas.shell-users
```

Hash password
-------------

```sh
sudo apt-get install whois
mkpasswd --method=sha-512
```

Example Playbook
----------------

```yaml
- name: provision servers
  hosts: all
  become: true
  roles:
    - { role: 'salamachinas.shell-users', tags: 'shell-users' }
  vars:
    users:
      - {name: 'ansible', password: '$1$xyz$IfAWr/Pbmpx80TTPdTZV.0'}
      - {name: 'example', password: '$1$xyz$IfAWr/Pbmpx80TTPdTZV.0'}
    authorized:
      - 'ansible'
    shell:
      - {name: 'example', binary: /bin/false}
```

Tests
-----

```sh
docker build -t test-ansible-shell-users-centos7 -f tests/Dockerfile_centos7 --force-rm .
docker build -t test-ansible-shell-users-debian7 -f tests/Dockerfile_debian7 --force-rm .
docker build -t test-ansible-shell-users-debian8 -f tests/Dockerfile_debian8 --force-rm .
docker build -t test-ansible-shell-users-ubuntu14 -f tests/Dockerfile_ubuntu14 --force-rm .
docker build -t test-ansible-shell-users-ubuntu16 -f tests/Dockerfile_ubuntu16 --force-rm .
```
