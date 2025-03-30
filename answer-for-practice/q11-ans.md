```j2
# myhosts.j2
127.0.0.1 localhost localhost.localdomain localhost4 localhost4.localdomain4  
::1 localhost localhost.localdomain localhost6 localhost.localdomain6
{% for i in groups[all] %}
{{ hostvars[i].ansible_default_ipv4.address }} {{ hostvars[i].ansible_fqdn }} {{ hostvars[i].ansible_hostname }}
{% endfor %}
```

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
$ ansible all -m shell -a "cat /etc/myhosts"
```
