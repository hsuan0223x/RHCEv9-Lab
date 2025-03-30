1. install ansible
```shell
$ sudo dnf install ansible-core -y
```
2. create file
```shell
mkdir ansible
cd ansible
mkdir roles
mkdir mycollections
touch inventory
```
3. write `inventory` file
```
[dev]
node1

[test]
node2

[prod]
node[3:4]

[balancers]
node5

[webservers:children]
prod
```
4. test `inventory` file
```shell
$ ansible [group name] -i inventory --list-hosts
```
5. edit `ansible.cfg` file
```shell
$ ansible-config init --disabled > ansible.cfg
```
```
[defaults]
inventory = inventory
remote_user = student
collections_path = mycollections
roles_path = roles
[privilege_escalation]
become = True
become_method = sudo
become_user = root
become_ask_pass = False
```
6. check `ansible.cfg` file
```shell
$ ansible all -m ping
```