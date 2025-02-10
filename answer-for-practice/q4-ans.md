1. cd to collection file
```shell
$ cd ~/ansible/mycollections
```
2. write request.yml
```yml
collections:
    - name: https://galaxy.ansible.com/download/community-general-5.5.0.tar.gz
    - name: https://galaxy.ansible.com/download/ansible-posix-1.5.1.tar.gz
```
3. run the command
```shell
$ ansible-galaxy collection install -r request.yml -p .
```