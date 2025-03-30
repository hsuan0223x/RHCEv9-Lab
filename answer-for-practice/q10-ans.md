1. yaml file
```yaml
- name: Copy inline content to /etc/issue
  hosts: all
  tasks:
    - name: Copy content to /etc/issue based on group
      ansible.builtin.copy:
        content: "{{ item.cont }}"
        dest: /etc/issue
      when: item.grp in group_names
      loop:
        - cont: "Development"
          grp: "dev"
        - cont: "Test"
          grp: "test"
        - cont: "Production"
          grp: "prod"
```
2. test
```shell
$ ansible dev,test,prod -m command -a "cat /etc/issue"
```
