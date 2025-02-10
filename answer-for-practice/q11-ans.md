```yaml
- name: Generate an /etc/myhosts file for dev only
  hosts: all
  tasks:
    - name: Grab and fill-in the template myhosts.j2
      ansible.builtin.template:
        src: myhosts.j2
        dest: /etc/myhosts
      when: "'dev' in group_names"
```

```shell
$ ansible all -m shell -a "cat /etc/myhosts; echo ' '"
```