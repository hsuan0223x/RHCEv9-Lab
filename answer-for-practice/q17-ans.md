1. install `rhel-system-roles` package
```shell
$ sudo yum install rhel-system-roles -y
```
2. copy collection to `mycollections` directory
```shell
$ cp -rf /usr/share/ansible/collections/ansible_collections/redhat /home/rocky/ansible/mycollections/ansible_collections
```
3. copy role file to `roles` directory
```shell
$ cp -rf /usr/share/ansible/roles/rhel-system-roles.timesync ~/ansible/roles
```
4. write `timesync.yml`
```yml
- hosts: all
  vars:
    timesync_ntp_servers:
      - hostname: 172.28.128.100
        iburst: yes
  roles:
    - rhel-system-roles.timesync
```
5. run and test playbook
```shell
$ ansible-playbook timesync.yml
$ ansible all -m shell -a "/etc/chrony.conf"
```