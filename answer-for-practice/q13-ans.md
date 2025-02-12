1. download the file `user_list.yml`
```shell
$ wget https://github.com/hsuan0223x/RHCEv9-Lab/blob/main/practice-exam-question/files/user_list.yml
```
2. create users.yml
```yaml
- name: Create developer users
  hosts: dev,test
  vars_files:
    - user_list.yml
    - locker.yml
  tasks:
    - name: Create the groups
      ansible.builtin.group:
        name: opsdev
        state: present

    - name: add users who have developer job
      ansible.builtin.user:
        name: "{{ item.name }}"
        groups: opsdev
        password: "{{ pw_developer | password_hash('sha512') }}"
      when: item.job == 'developer'
      loop: "{{ users }}"

- name: Create manager users
  hosts: prod
  vars_files:
    - user_list.yml
    - locker.yml
  tasks:
    - name: Create the groups
      ansible.builtin.group:
        name: opsmgr
        state: present

    - name: add users who have manager job
      ansible.builtin.user:
        name: "{{ item.name }}"
        groups: opsmgr
        password: "{{ pw_manager | password_hash('sha512') }}"
      when: item.job == 'manager'
      loop: "{{ users }}"
```
3. run playbook
```shell
$ ansible-playbook ansible-playbook users.yml --vault-id secret.txt 
```
4. test
```shell
$ ansible all -m shell -a "getent group opsdev"
$ ansible all -m shell -a "getent group opsmgr"
```