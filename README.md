# My Ansible Locker Room of Ansible Playbooks and related notes

## Descriptions
1: basic configuration for getting a system up and running

2: configuring kali repos and installing limited tools

5: configuring more of the system leveraging kali repos for teh packages

99: sample playbook for creating multiple users with random passwords


#### sample commands for future reference(s)
```
ansible pi -i inventory.txt -m ping -k -K 
```

```
ansible-playbook playbook_5_basic_setup_plus_cmds.yml -i inventory.txt -k -K
```

```
ansible-playbook create_users_w_passwords.yml -i inventory.txt -k -K
```