# Install PowerDNS and PowerDNS-Admin using Ansible on Ubuntu 20 
### Adjust with your env
- #### <i> vars.yaml </i>
```
---
pdns_master_ip: "{{ hostvars['master']['ansible_host'] }}"
pdns_slave_ip: "{{ hostvars['slave']['ansible_host'] }}"
pdns_api_key: YhGGfFFlK8hJkwlF
pdns_loglevel: 5
pdns_webserver_password: Zm3wTfyeiLBXkUv2
pdns_webserver_port: 8081
pdns_webserver_allow_from: 0.0.0.0/0

mariadb_version: 10.6
mariadb_vol_dir: /opt/mariadb
mariadb_root_password: LYSvPiRE8AYVIOMh
mariadb_user: pdns
mariadb_password: H5BHrFXsjtFxgRDZ
mariadb_database: pdns
mariadb_host: "{{ ansible_host }}"
mariadb_expose_port: 3306

pdns_admin_database: pdns_admin
pdns_admin_expose_port: 9191
pdns_admin_seckey: UGP8Wy4OQaPqHnCE

domain_name: test.xyz
...
```
- #### <i> hosts </i>
```
[pdns]
master ansible_host=192.168.90.51
slave  ansible_host=192.168.90.52

[all:vars]
ansible_user=user
ansible_ssh_pass=P4s5word
ansible_become_password=P4s5word
```
### Run playbook
```
ansible-playbook -i hosts playbook.yaml
```
### Access PoweDNS-Admin dashboard
http://192.168.90.51:9191/

![image](https://github.com/bangze-93/powerdns-master-slave/assets/52735927/d689cb12-3a15-44a4-83ef-4f2a16755a2c)

