# Question 13

## Download the variable file

`https://github.com/hsuan0223x/RHCEv9-Lab/blob/main/practice-exam-question/files/user_list.yml` and write a playbook named `users.yml` and then run the playbook
on all the nodes using two variable files `user_list.yml` and `locker.yml`.

1. 
    * Create a group opsdev
    * Create user from users varaible who job is equal to developer and need to be in opsdev group
    * Assign a password using SHA512 format and run playbook on dev and test group.
    * User password is {{ pw_developer }}

2. 
    * Create a group opsmgr
    * Create user from users varaible who job is equal to manager and need to be in opsmgr group
    * Assign a password using SHA512 format and run playbook on prod group.
    * User password is {{ pw_manager }}

3. Use when condition for each play