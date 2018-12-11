## Install apache2 (httpd alternative)
ansible-doc apt 
ansible web -i inventory_test -m apt -a "name=apache2 state=present" --become

## Apache Service: auto start on boot, state started
ansible-doc service
ansible web -i inventory_test -m service -a "name=apache2 enabled=yes state=started" --become

## Install mysqld
ansible db -i inventory_test -m apt -a "name=mysqld state=present" --become

## Module
- setup
```
ansible all -i inventory_test -m setup -a "filter=ansible_en*" 
ansible all -i inventory_test -m setup -a "filter=ansible_mounts"
ansible all -i inventory_test -m setup -a "filter=ansible_mounts" --tree ./setup
```
# Error:

## Failed to connect to the host via ssh, WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!
- ```sudo nano ~/.ssh/known_hosts```, remove some known_hosts related to these hosts above
- install sshpass ```sudo apt-get install sshpass```
- add ```host_key_checking=False``` to ```ansible.cfg```
```cfg
[defaults]
host_key_checking=False
```
- tmr solution: specify ```-u vagrant -k``` and type password ```vagrant``` by default
