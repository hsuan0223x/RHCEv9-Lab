# Question 17

## Use a RHEL `timesync` system role:

- Create a playbook called "timesync.yml" that:
  - Runs on all managed nodes
  - Uses the timesync role
  - Configures the role to use the currently active NTP provider
  - Configure the role to use the time server classroom.lab.example.com
  - Configure the role to enable the iburst parameter

# For this example we will use our ansible control node to sync up with