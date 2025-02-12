1. create file
```shell
# PASSWORD = 123
$ ansible-vault create salaries.yml
New Vault password:
Confirm New Vault password:
```
2. rekey file
```shell
$ ansible-vault rekey salaries.yml
Vault password:
New Vault password:
Confirm New Vault password:
Rekey successful
```