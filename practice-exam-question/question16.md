# Question 16

## Create a logical volume
- Verify if the volume group research does not exist, and if so, display the debug message:
  - "Volume Group research not found".
- If the requested logical volume size (1500 MiB) cannot be created, display the debug message:
  - "Could not create a logical volume of that size. Using 800 MiB instead."
  - and proceed to create an 800 MiB volume.
- If the logical volume is created, assign the file system as `ext4`.
- Do NOT mount the logical volume in any way.
- The playbook name is `lv.yml` and it should run on all managed nodes.