# Confluent Cluster

## Intro

Create a confluent cluster using Confluent community edition and Docker (yes, community edition...too)

## Requirements

* 3 nodes running Centos 7 
* selinux enabled
* firewalld enabled
* docker-ce v.17.0.3
* Ansible >= 2.3

## Install

* Define your servers in your inventory file.

* Run the playbook using this inventory.

Example:

```
sudo ansible-playbook site.yml -i inventory
```

To check the installation: 

```
[juan.enciso@satelite confluent-cluster]$ sudo ansible -i inventory -m shell -a "docker ps -a" confluent-cluster            
confluent02.iplanet.work | SUCCESS | rc=0 >>
CONTAINER ID        IMAGE                                   COMMAND                  CREATED             STATUS              PORTS               NAMES
a4f44e608bf7        confluentinc/cp-kafka-rest:3.2.1        "/etc/confluent/do..."   5 hours ago         10 seconds                              kafka-rest
6cefd811e43a        confluentinc/cp-schema-registry:3.2.1   "/etc/confluent/do..."   5 hours ago         10 seconds                              schema-registry
2b8f602d9c2d        confluentinc/cp-kafka:3.2.1             "/etc/confluent/do..."   5 hours ago         10 seconds                              kafka
38b6a9f4e7bb        confluentinc/cp-zookeeper:3.2.1         "/etc/confluent/do..."   5 hours ago         10 seconds                              zk

confluent02.iplanet.work | SUCCESS | rc=0 >>
CONTAINER ID        IMAGE                                   COMMAND                  CREATED             STATUS              PORTS               NAMES
30ed1efd16ce        confluentinc/cp-kafka-rest:3.2.1        "/etc/confluent/do..."   5 hours ago         10 seconds                              kafka-rest
ba148a13acc3        confluentinc/cp-schema-registry:3.2.1   "/etc/confluent/do..."   5 hours ago         10 seconds                              schema-registry
c78e3d9effa9        confluentinc/cp-kafka:3.2.1             "/etc/confluent/do..."   5 hours ago         10 seconds                              kafka
7176a584768b        confluentinc/cp-zookeeper:3.2.1         "/etc/confluent/do..."   5 hours ago         10 seconds                              zk

confluent01.iplanet.work | SUCCESS | rc=0 >>
CONTAINER ID        IMAGE                                   COMMAND                  CREATED             STATUS              PORTS               NAMES
a9a3f4e623b6        confluentinc/cp-kafka-rest:3.2.1        "/etc/confluent/do..."   5 hours ago         10 seconds                              kafka-rest
55aee8c87e3c        confluentinc/cp-schema-registry:3.2.1   "/etc/confluent/do..."   5 hours ago         10 seconds                              schema-registry
694f4b01d90e        confluentinc/cp-kafka:3.2.1             "/etc/confluent/do..."   5 hours ago         10 seconds                              kafka
7b3878c7aeb6        confluentinc/cp-zookeeper:3.2.1         "/etc/confluent/do..."   5 hours ago         10 seconds                              zk

[juan.enciso@satelite confluent-cluster]$ 
```

## Notes

if you are behind of a proxy server, setup the variable ***proxy_enabled: True***


## Author

Juan Enciso 

juan.enciso@gmail.com
