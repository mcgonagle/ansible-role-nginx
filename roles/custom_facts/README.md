#Isomorphism and Custom Facts

##Isomoprhic Hostname
* wwwplqa01.cam.example.net
    * www -> role
    * pl -> product
    * qa -> zone
    * 01 -> hostid
* wwwplqa01-> hostname
* cam -> datacenter
* example.net -> domain
* wwwplqa01.cam.example.net -> fqdn

##Isomoprhic IP Addresses
* 10.1.1.1
    * 10.1 -> datacenter   
    * 10.1.1 -> zone/product
    * 10.1.1.1 -> possible role

##Ansible Gather Facts Command
```
(ansible)$ ansible nginx -m setup --private-key ~/Dropbox/Ansible_Playbook/.vagrant/machines/default/virtualbox/private_key -u vagrant
```

```
(ansible)$ ansible nginx -m setup -a 'filter=ansible_local' --private-key ~/Dropbox/Ansible_Playbook/.vagrant/machines/default/virtualbox/private_key -u vagrant
```

