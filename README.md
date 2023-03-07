# Ansible Playbook

Playbook for preparing docker-compose servers based on debian or redhat systems

## Steps

* upgrade system
* install docker
* install docker-compose
* configure basic iptables rules and install iptables service for making them persistent

## Iptables

Configured iptables rules allow only ssh external connections and deny all the rest

## Usage

Make inventory file

```
my.server.com ansible_user=user1
...
```
Run playbook:

```
ansible-playbook -i <inventory-file> -b prepare_serv.yaml --ask-pass -K
```
You can also specify tags for making only nessesary operations:
```
ansible-playbook -i <inventory-file> -b prepare_serv.yaml --ask-pass -K --tags=docker,docker-compose
```
