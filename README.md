# Install PowerDNS and PowerDNS-Admin with Ansible on Ubuntu 20
### Adjust with your env
- #### <i> vars.yaml </i>
```
---
master_ip: "{{ hostvars['master']['ansible_host'] }}"
slave_ip: "{{ hostvars['slave']['ansible_host'] }}"
api_key: mzlcV0ROmd0ZVZqo
loglevel: 5
db_host: localhost
db_port: 3306
db_name: pdns
db_user: pdns
db_pass: Pdn5DBP4ss!
db_name_admin: pdns_admin
db_user_admin: pdns-admin
db_pass_admin: Pdn5DBAdmP4ss!
...
```
- #### <i> hosts </i>
```
[pdns]
master ansible_host=192.168.200.41
slave  ansible_host=192.168.200.42

[all:vars]
ansible_connection=ssh
ansible_user=user
ansible_ssh_pass=P4s5word
ansible_become_password=P4s5word
```
### Run playbook
```
ansible-playbook -i hosts playbook.yaml
```
### Access PoweDNS-Admin dashboard
http://192.168.200.41:9191/

![image](https://github.com/bangze-93/powerdns-master-slave/assets/52735927/d689cb12-3a15-44a4-83ef-4f2a16755a2c)

