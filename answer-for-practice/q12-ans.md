1.
```shell
$ vim secret.txt
# whenyouwishuponastar
```
2. 
```shell
$ ansible-vault create locker.yml --vault-password-file=secret.txt
```
3.
```shell
$ ansible-vault view locker.yml --vault-password-file=secret.txt
```