# Quick notes
## Install apache2 (httpd alternative)
- ansible-doc apt 
- ansible web -i inventory_test -m apt -a "name=apache2 state=present" --become

## Apache Service: auto start on boot, state started
- ansible-doc service
- ansible web -i inventory_test -m service -a "name=apache2 enabled=yes state=started" --become

### Install mysqld
- ansible db -i inventory_test -m apt -a "name=mysqld state=present" --become

## Module
- setup
```
ansible all -i inventory_test -m setup -a "filter=ansible_en*" 
ansible all -i inventory_test -m setup -a "filter=ansible_mounts"
ansible all -i inventory_test -m setup -a "filter=ansible_mounts" --tree ./setup
```

## Playbook
- Plays are ordered sets of tasks to execute against host selections from your inventory
- Playbook is a file containing one or more plays
- notify handles from task and handlers
- condition clause: based on os family (```when: ansible_os_family == "Debian"```), based on output
- using template: Jinja2 Engine

## Roles => Making your playbooks reusable
- Roles are a packages of closely related Ansible content that can be shared more easily than plays alone
- pre_tasks, post_tasks
- import_playbook: webservers.yml

##


# Errors:

## Failed to connect to the host via ssh, WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!
- ```sudo nano ~/.ssh/known_hosts```, remove some known_hosts related to these hosts above
- install sshpass ```sudo apt-get install sshpass```
- add ```host_key_checking=False``` into ```ansible.cfg```
```
[defaults]
host_key_checking=False
```
- tmr solution: specify ```-u vagrant -k``` and type password ```vagrant``` by default

# Questions

- ssh, yum packages: https://github.com/phongnx1/ansible-docker-training/blob/master/Vagrantfile
