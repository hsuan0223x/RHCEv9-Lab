1. create apache offline role
```shell
$ cd ~/ansible/roles
$ ansible-galaxy role init --offline apache
# Role apache was created successfully
```
2. create "template.j2" file (please search practice-exam-question/files/template.j2 )
```shell
$ cd apache/templates
$ vim template.j2
```
3. edit task yaml
```shell
$ cd ../tasks
$ vim main.yml
```
```yaml
- name: install httpd and firewalld
  ansible.builtin.dnf:
    name:
      - httpd
      - firewalld
    state: latest

- name: start both services
  ansible.builtin.service:
    name: "{{ item }}"
    state: restarted
    enabled: yes
  loop:
    - httpd
    - firewalld

- name: add http service to the firewall rule
  ansible.posix.firewalld:
    service: http
    state: enabled
    permanent: yes
    immediate: yes

- name: copy the template.j2 file to the webserver directory
  ansible.builtin.template:
    src: template.j2
    dest: /var/www/html/index.html
```
4. create `apache_role.yml` file
```shell
$ cd ~/ansible
$ vim apache_role.yml
```
```yaml
- hosts: webservers
  roles:
    - apache
```
5. run and test this playbook
```
$ ansible-playbook apache_role.yml
$ curl node5
```