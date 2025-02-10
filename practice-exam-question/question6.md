# Question 6

## Create Offline Role For Apache

Create an offline role named `apache` under the `roles` directory.
- install the httpd package and the service should be started and enabled.
- host the webpage using the `template.j2` ( this project will supply )
- the `template.j2` should contain:
  - Welcome to HOSTNAME ON IPADDRESS
  - where hostname is the Fully Qualified Domain Name (FQDN)
- create the playbook called `apache_role.yml` and run the role on the webservers group.