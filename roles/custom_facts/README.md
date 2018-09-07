# Autonomic Isomorphism and Ansible Custom Facts

## Isomoprhic Hostname
* wwwplqa01.cam.example.net
    * www -> role
    * pl -> product
    * qa -> zone
    * 01 -> hostid
* wwwplqa01-> hostname
* cam -> datacenter
* example.net -> domain
* wwwplqa01.cam.example.net -> fqdn

## Isomoprhic IP Addresses
* 10.1.1.1
    * 10.1 -> datacenter   
    * 10.1.1 -> zone/product
    * 10.1.1.1 -> possible role

## Metrics Driven Autonomic Computing
```
#!/bin/bash

connections=$(curl -s http://localhost/api/3/connections/)

echo $connections
```

```
#!/bin/bash

upstreams=$(curl -s http://localhost/api/3/http/upstreams/)

echo $upstreams
```

```
(ansible)$ ansible nginx -m setup -a 'filter=ansible_local' --private-key ~/Dropbox/Ansible_Playbook/.vagrant/machines/default/virtualbox/private_key -u vagrant
10.42.0.43 | SUCCESS => {
    "ansible_facts": {
        "ansible_local": {
            "connections": {
                "accepted": 3445,
                "active": 1,
                "dropped": 0,
                "idle": 1
            },
            "datacenter": {
                "name": "cam.example.net"
            },
            "domain": {
                "name": "cam.example.net"
            },
            "pool": {
                "servers": [
                    "server1",
                    "server2",
                    "server3"
                ]
            },
            "product": {
                "name": "pl"
            },
            "role": {
                "name": "www"
            },
            "upstreams": {
                "backend": {
                    "keepalive": 0,
                    "peers": [
                        {
                            "active": 0,
                            "backup": false,
                            "downtime": 0,
                            "fails": 0,
                            "health_checks": {
                                "checks": 373,
                                "fails": 0,
                                "last_passed": true,
                                "unhealthy": 0
                            },
                            "id": 0,
                            "name": "127.0.0.1:8086",
                            "received": 0,
                            "requests": 0,
                            "responses": {
                                "1xx": 0,
                                "2xx": 0,
                                "3xx": 0,
                                "4xx": 0,
                                "5xx": 0,
                                "total": 0
                            },
                            "sent": 0,
                            "server": "127.0.0.1:8086",
                            "state": "up",
                            "unavail": 0,
                            "weight": 1
                        },
                        {
                            "active": 0,
                            "backup": false,
                            "downtime": 0,
                            "fails": 0,
                            "health_checks": {
                                "checks": 373,
                                "fails": 0,
                                "last_passed": true,
                                "unhealthy": 0
                            },
                            "id": 1,
                            "name": "127.0.0.1:8081",
                            "received": 0,
                            "requests": 0,
                            "responses": {
                                "1xx": 0,
                                "2xx": 0,
                                "3xx": 0,
                                "4xx": 0,
                                "5xx": 0,
                                "total": 0
                            },
                            "sent": 0,
                            "server": "127.0.0.1:8081",
                            "state": "up",
                            "unavail": 0,
                            "weight": 1
                        },
                        {
                            "active": 0,
                            "backup": false,
                            "downtime": 0,
                            "fails": 0,
                            "health_checks": {
                                "checks": 373,
                                "fails": 0,
                                "last_passed": true,
                                "unhealthy": 0
                            }
                      ],
                    "zombies": 0,
                    "zone": "backend"
                }
            },
            "zone": {
                "name": "qa"
            }
        }
    },
    "changed": false
}

```

## Autonomic Computing Characteristics
[Autonomic Computing Characteristics](https://en.wikipedia.org/wiki/Autonomic_computing#Characteristics_of_autonomic_systems)

The system must:

1. know itself in terms of what resources it has access to, what its capabilities and limitations are and how and why it is connected to other systems;
2. be able to automatically configure and reconfigure itself depending on the changing computing environment;
3. be able to optimize its performance to ensure the most efficient computing process;
4. be able to work around encountered problems by either repairing itself or routing functions away from the trouble;
5. detect, identify and protect itself against various types of attacks to maintain overall system security and integrity;
6. adapt to its environment as it changes, interacting with neighboring systems and establishing communication protocols;
7. rely on open standards and cannot exist in a proprietary environment;
8. anticipate the demand on its resources while staying transparent to users.


## Ansible Gather Facts Command
```
(ansible)$ ansible nginx -m setup --private-key ~/Dropbox/Ansible_Playbook/.vagrant/machines/default/virtualbox/private_key -u vagrant
```
## Ansible Gather Defined Custom Facts Command
```
(ansible)$ ansible nginx -m setup -a 'filter=ansible_local' --private-key ~/Dropbox/Ansible_Playbook/.vagrant/machines/default/virtualbox/private_key -u vagrant
```

