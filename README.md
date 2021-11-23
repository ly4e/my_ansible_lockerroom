# My Ansible Locker Room of Playbooks and Notes
A collection of playbooks and ansible related notes.
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

```
ansible-playbook <playbookname.yml> -c local -i "localhost,"
```

### trouble shooting packages
`pip3 install docker yamllint ansible-lint`


### other stuff

```
ansible -i inventory example -m ping -u centos
#or
ansible example -a "free -h" -u centos
#or
ansible -i inventory db -m setup
#or
ansible -i inventory multi -a "date"
#or 
ansible -i inventory multi -b -m yum -a "name=ntp state=present"

```
---
---
---
## More misc commands to clean up later ##
```
    ansible-playbook playbook_0_do_nothing.yml --limit=kube --private-key=~/.ssh/custom_ansi
    ansible-playbook playbook_0_do_nothing.yml --limit=U642 --private-key=~/.ssh/custom_ansi
    ansible-playbook playbook_0_do_nothing.yml -k -K
    ansible-playbook playbook_0_do_nothing.yml -k -K --limit=U641
    ansible-playbook playbook_61_keyed_user_creation.yml -k -K --limit=U641
    ssh -i ~/.ssh/custom_ansi ansi@192.168.105.219
    ssh -i ~/.ssh/custom_ansi ansi@192.168.105.50
    ssh 192.168.105.219
    ssh 192.168.105.50

```


#### manually installing `sshpass` on MacOS for those times when keys are not in place...
```
### Reference: https://stackoverflow.com/questions/32255660/how-to-install-sshpass-on-mac  ###
curl -O -L  https://fossies.org/linux/privat/sshpass-1.09.tar.gz && tar xvzf sshpass-1.09.tar.gz
cd sshpass-1.09/
./configure
sudo make install
```