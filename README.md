# Confluent Cluster

## Intro

Create a confluent cluster using Confluent community edition and Docker (yes, community edition...too)

## Requirements

* 3x Centos 7 servers 
* selinux
* firewalld
* Ansible >= 2.3

## Install

* Define your servers in inventory file.

* Run the playbook using this inventory.

Example:

```
sudo ansible-playbook site.yml -i inventory
```

## Author

Juan Enciso 

juan.enciso@gmail.com
