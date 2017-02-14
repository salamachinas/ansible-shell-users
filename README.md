ansible-shell-users
===================

This role manage shell users

[![Ansible Galaxy](https://img.shields.io/ansible/role/xxxxxxx.svg)](https://galaxy.ansible.com/salamachinas/shell-users/)

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
openssl passwd -1 -salt xyz s3cr3t
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
