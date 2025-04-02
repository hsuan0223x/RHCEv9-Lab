# Question 2

## Setup yum Repo

As a system administrator, you need to install software on managed nodes.

Follow the instructions below to create a file named:
`/home/rocky/ansible/yum_repo.yml`
to install YUM repositories on each managed node.

Repository 1:
- Repository Name: EX294_BASE
- Description: EX294 base software
- Base URL: https://download.rockylinux.org/pub/rocky/9/BaseOS/x86_64/os/
- GPGkey: https://download.rockylinux.org/pub/rocky/RPM-GPG-KEY-rockyofficial
- Repository Status: Enabled

Repository 2:
- Repository Name: EX294_STREAM
- Description: EX294 stream software
- Base URL: https://download.rockylinux.org/pub/rocky/9/AppStream/x86_64/os/
- GPGkey: https://download.rockylinux.org/pub/rocky/RPM-GPG-KEY-rockyofficial
- Repository Status: Enabled
