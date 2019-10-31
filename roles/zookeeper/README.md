Role Name
=========

Kafka role which will install and config kafka_2.11-0.11.0.0.

Requirements
------------

GCP firewall tags should be added in to according to kafka and zookeeper playbooks

This will only run and tested in centos 7 environment and only config for that environment it self

Role Variables
--------------
```
vars/main.yml

# vars file for kafka
kafka_src: https://archive.apache.org/dist/kafka/0.11.0.0/kafka_2.11-0.11.0.0.tgz
kafka_folder: kafka_2.11-0.11.0.0

templates/zookeeper.cfg

# templates file
This will auto added all brokers and zookeepers for kafka
clientPortAddress= <>
server.{{loop.index}}= <>

templates/myid

<This will add id for each hosts>

```
Dependencies
------------

This will install all the depedencies, But You must spinup zookeeper and kafka instances with requested firewall tags

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:
```
---
- hosts: tag_zookeeper-ansible  <THIS IS MY ZOOKEEPER FIREWALL TAG>
  sudo: yes
  roles: 
   - zookeeper
```
License
-------

BSD

Author Information
------------------

Ansible was created by [Thulasya Rajakaruna](https://github.com/thulasya)
