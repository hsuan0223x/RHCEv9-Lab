# RHCEv9-Lab 

## Environment Setup

1. Prepare 6 VMs ( Rocky Linux or RHEL ).
2. Configure hostname and IP for each VM.
3. Delete all files in `/etc/yum.repo.d/*` on managed nodes.
4. Configure the `/etc/hosts` file on the control node.
5. set up no password sudo and copy SSH keys using `ssh-copy-id`.

| hostname |        FQDN         |   IP address   |
|:--------:|:-------------------:|:--------------:|
| control  | control.example.com | 192.168.10.100 |
|  node1   |  node1.example.com  | 192.168.10.101 |
|  node2   |  node2.example.com  | 192.168.10.102 |
|  node3   |  node3.example.com  | 192.168.10.103 |
|  node4   |  node4.example.com  | 192.168.10.104 |
|  node5   |  node5.example.com  | 192.168.10.105 |
