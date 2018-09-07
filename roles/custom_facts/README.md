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

