1. write hwreport.yml
```yaml
- name: Generate a hw report
  hosts: all
  tasks:
    - name: Download foo.conf
      ansible.builtin.get_url:
        url: https://raw.githubusercontent.com/hsuan0223x/RHCEv9-Lab/refs/heads/main/practice-exam-question/files/hwreport.txt
        dest: /root/hwreport.txt
        mode: '0755'

    - name: Replace old hostname with new hostname (requires Ansible >= 2.4)
      ansible.builtin.replace:
        path: /root/hwreport.txt
        regexp: "{{ item.oldinfo }}"
        replace: "{{ item.newinfo }}"
      loop:
        - oldinfo: "inventoryhostname"
          newinfo: "{{ ansible_hostname | default ('NONE') }}"
        - oldinfo: "memory_in_MB"
          newinfo: "{{ ansible_memory_mb.real.free | default ('NONE') }}"
        - oldinfo: "BIOS_version"
          newinfo: "{{ ansible_bios_version | default ('NONE') }}"
        - oldinfo: "disk_sda_size"
          newinfo: "{{ ansible_devices.sda.size | default ('NONE') }}"
        - oldinfo: "disk_sdb_size"
          newinfo: "{{ ansible_devices.sdb.size | default ('NONE') }}"
```
2. test
```shell
$ ansible all -m shell -a "cat /root/hwreport.txt; echo ' '"
```