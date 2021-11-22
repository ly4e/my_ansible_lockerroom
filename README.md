# My Ansible Locker Room of Playbooks and Notes

## Descriptions
### playbook_1_init_system_configuration:
> basic configuration for getting a system up and running
> 
> Installs some basic packages, VSCode, zgenom, my dotfile repo, and the Pentesters Framwork (PTF)

### playbook_2_add_and_install_from_kali_repos:
> configures kali-rolling with its certificate and installs limited tools then removes the Kali repo from the sources.list
> 
> currently leaves an extra commented out version of the kali repo for ease of searching and testing

### playbook_5_basic_setup_plus_cmds:
> basic configuration for getting a system up and running
> 
> Installs more packages from the kali-rolling repo
>
> (more of a combination of playbooks 1 and 2)

### playbook_99_creating_extra_users_w_rand_passwords:
> sample playbook: creates multiple user accounts with random passwords



---
---
---
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

to limit which host it is running on from the scope it already has...
```
ansible-playbook create_users_w_passwords.yml -i inventory.txt -k -K --limit=controller
```