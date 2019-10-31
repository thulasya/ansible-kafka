# ansible
GCE ansible repo

# This Repo included

1) Inventry for Google Cloud Engine

2) ansible.cfg file which has enabled requested plugins and settings 
  * In .cfg file add your gcp .ssh/id_rsa file which will help to ssh in to ansible for GCP instances
  ```
    private_key_file = /etc/ansible/keys/<your key>
 ``` 
3) Playbooks and roles folders which will install and config kafka and Zookeeper in to your servers

# Inventry

You could refer original repo, which I was refering in below link, I have changed some as for my environment.

https://github.com/ansible/ansible/tree/devel/contrib/inventory
```
# Playbooks

1) zookeeper tree
zookeeper/
└── zookeeper_instance.yml 


- hosts: <zookeeper firewall tag>
  
2) kafka tree
kafka/
└── kafka_instance.yml


- hosts: <kafka firewall tag>

# Roles

1) kafka tree
kafka/
├── README.md
├── defaults
│   └── main.yml
├── files
│   └── readme.md
├── handlers
│   └── main.yml
├── meta
│   └── main.yml
├── tasks
│   └── main.yml
├── templates
│   └── server.cfg
├── tests
│   ├── inventory
│   └── test.yml
└── vars
    └── main.yml
    
    
2) Zookeeper tree
zookeeper/
├── README.md
├── defaults
│   └── main.yml
├── files
│   └── readme.md
├── handlers
│   └── main.yml
├── meta
│   └── main.yml
├── tasks
│   └── main.yml
├── templates
│   ├── myid
│   └── zookeeper.cfg
├── tests
│   ├── inventory
│   └── test.yml
└── vars
    └── main.yml
<Refer to more info in role readme>
```
