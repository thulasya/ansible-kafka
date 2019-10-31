Role Name
=========

Kafka role which will install and config confluent-5.0.0-2.11.

Requirements
------------

GCP firewall tags should be added in to according to kafka and zookeeper playbooks

This will only run and tested in centos 7 environment and only config for that environment it self

Role Variables
--------------
```
vars/main.yml

# vars file for kafka
confluent: http://packages.confluent.io/archive/5.0/confluent-5.0.0-2.11.tar.gz
confluent_folder: confluent-5.0.0

templates/server.cfg

# templates file
This will auto added all brokers and zookeepers for kafka
broker.id= <>
listeners= <>
zookeeper.connect= <>

```
Dependencies
------------

This will install all the depedencies, But You must spinup zookeeper and kafka instances with requested firewall tags

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:
```
---
- hosts: tag_ansible-kafka  <THIS IS MY KAFKA FIREWALL TAG>
  sudo: yes
  roles: 
   - kafka
```
License
-------

BSD

Author Information
------------------

Ansible was created by [Thulasya Rajakaruna](https://github.com/thulasya)
