11. Download file "https://github.com/hsuan0223x/RHCEv9-Lab/blob/main/practice-exam-question/files/myhosts.j2"

  1) myhosts.j2 is having the content:
        ```
       127.0.0.1 localhost localhost.localdomain localhost4 localhost4.localdomain4  
       ::1 localhost localhost.localdomain localhost6 localhost.localdomain6
        ```

  ii) The file should collect all node information like ipaddress,fqdn,hostname
       and it should be same as `/etc/hosts` file,
       if playbook is run on all the managed nodes it must store in `/etc/myhosts`.

Finally /etc/myhosts should like as below:
```
127.0.0.1 localhost localhost.localdomain localhost4 localhost4.localdomain4
::1 localhost localhost.localdomain localhost6 localhost.localdomain6

192.168.10.100   control.example.com   control
192.168.10.101   node1.example.com     node1
192.168.10.102   node2.example.com     node2
192.168.10.103   node3.example.com     node3
192.168.10.104   node4.example.com     node4
192.168.10.105   node5.example.com     node5
```

iii) The playbook name should be "hosts.yml" and run it on dev group.