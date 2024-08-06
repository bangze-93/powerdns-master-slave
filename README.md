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
ansible-playbook playbook.yaml
```
### Access PoweDNS-Admin dashboard
http://192.168.90.51:9191/
![Screenshot from 2024-08-06 11-42-09](https://github.com/user-attachments/assets/7cdfe5e5-b8c5-4bd8-9c4c-c65879751ed3)
![Screenshot from 2024-08-06 11-43-05](https://github.com/user-attachments/assets/bf288fb4-2e62-4a47-8b1c-41ceeb8b1fee)
![Screenshot from 2024-08-06 11-48-11](https://github.com/user-attachments/assets/b58a6ed1-130d-4fc7-a028-3a9958518b1f)
![Screenshot from 2024-08-06 11-48-32](https://github.com/user-attachments/assets/0cb39e8b-c03e-4094-90bf-326a1217cd26)
![Screenshot from 2024-08-06 11-50-18](https://github.com/user-attachments/assets/6c0fbf79-7616-4055-8eaa-5e3e00c8a15d)



