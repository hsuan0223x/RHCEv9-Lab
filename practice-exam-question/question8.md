# Question 8

## Create a playbook should run on webservers group.
- create webcontent.yml
  - create a directory /webdev and it should be owned by wheel group.
  - Assign permissions for user=rwx, group=rwx, others=rx and group special permission should be applied to /webdev.
  - /webdev directory should have the same selinux context type as "httpd" (httpd_sys_content_t)
  - Create a soft link /webdev to /var/www/html/webdev.
  - Create index.html file under /webdev and file should have content "Development".
  - Allow traffic through the firewall for http.