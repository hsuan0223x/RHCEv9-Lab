1. create roles.yml|
```yaml
- hosts: webservers
  roles:
    - phpinfo
- hosts: balancers
  roles:
    - balancer
```
2. Adjust the "~/ansible/roles/balancer/templates/balancer.j2"
```
#---------------------------------------------------------------------
# round robin balancing between the various backends
#---------------------------------------------------------------------
backend app
    balance     roundrobin
    server node3.example.com [node3 IP]:80 check
    server node4.example.com [node4 IP]:80 check

# OR WHATEVER YOUR WEBSERVERS ARE CONFIGURED AS ON THE RED HAT LAB
```
3. run playbook
```shell
$ ansible-playbook roles.yml
```
4. test
```shell
$ curl node5/hello.php
$ curl node5
```