1. install `rhel-system-roles` package
```shell
$ sudo yum install rhel-system-roles -y
# If you won't do this in lab 17
```
2. copy collection to `mycollections` directory
```shell
$ cp -rf /usr/share/ansible/collections/ansible_collections/redhat /home/rocky/ansible/mycollections/ansible_collections
# If you won't do this in lab 17
```
3. copy role file to `roles` directory
```shell
$ cp -rf /usr/share/ansible/roles/rhel-system-roles.selinux ~/ansible/roles
```
4. write `selinux.yml`
```yml
- name: configure selinux
  hosts: all
  vars:
    selinux_policy: targeted
    selinux_state: enforcing
  roles:
    - rhel-system-roles.selinux
```
5. run and test playbook
```shell
$ ansible-playbook selinux.yml
$ ansible all -m shell -a "getenforce"
```