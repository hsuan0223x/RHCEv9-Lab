# Question 1

Install and configure Ansible on the control node `control` as follows:

- Install the required packages.
- Create a static inventory file at `/home/rocky/ansible/inventory` that meets the following requirements:
    - `node1` is a member of the `dev` host group.
    - `node2` is a member of the `test` host group.
    - `node3` and `node4` are members of the `prod` host group.
    - `node5` is a member of the `balancers` host group.
    - The `prod` group is a member of the `webservers` host group.
- Create a configuration file at `/home/rocky/ansible/ansible.cfg` that meets the following requirements:
    - The inventory file is located at `/home/rocky/ansible/inventory`.
    - The roles used in playbooks are located at `/home/rocky/ansible/roles`.
    - The custom collections directory is `/home/rocky/ansible/mycollections`.
