# Ansible
# Docker

### Contents
- [Introduction](#introduction)
- [Basic implementation](#basic-implementation)
- [Flow control in playbook](#flow-control-in-playbook)
- [Way to Implement large Automation](#way-to-implement-large-automation)
- [Ansible GUI ](#ansible-gui )
- [References](#references)


## Introduction
-  [Ansible quickstart](https://docs.ansible.com/ansible/devel/user_guide/quickstart.html)
-  [YAML basics](https://www.tutorialspoint.com/ansible/ansible_yaml_basics.htm)
-  [Terminology](https://docs.ansible.com/ansible/devel/user_guide/basic_concepts.html)
-  [Installation](https://docs.ansible.com/ansible/latest/installation_guide/index.html)
-  [How ansible work](https://www.ansible.com/overview/how-ansible-works#:~:text=EFFICIENT%20ARCHITECTURE,and%20removes%20them%20when%20finished.)
-  [Getting started](https://docs.ansible.com/ansible/devel/user_guide/basic_concepts.html)
-  [First Innevtory](https://docs.ansible.com/ansible/devel/user_guide/intro_inventory.html)
-  [Ansible config file precedence](https://docs.ansible.com/ansible/latest/reference_appendices/config.html)


## basic Implementation 

-  [Ad hoc commands](https://www.tutorialspoint.com/ansible/ansible_ad_hoc_commands.htm#:~:text=Ad%20hoc%20commands%20are%20commands,usr%2Fbin%2Fansible'.)
-  [Run first playbook](https://docs.ansible.com/ansible/latest/network/getting_started/first_playbook.html)
-  [Working with modules](https://docs.ansible.com/ansible/latest/user_guide/modules.html)
-  [Ansible connection](https://docs.ansible.com/ansible/latest/user_guide/connection_details.html)
-  [Ansible Vault](https://docs.ansible.com/ansible/latest/user_guide/vault.html)
-  [privilege escalation](https://docs.ansible.com/ansible/latest/user_guide/become.html#using-become)
-  [setup module to gather facts] (https://docs.ansible.com/ansible/latest/modules/setup_module.html)
-  [Special variables](https://docs.ansible.com/ansible/latest/reference_appendices/special_variables.html)
-  [Ansible actions/Meta](https://docs.ansible.com/ansible/latest/modules/meta_module.html)


#### Assignnments
- write a adhoc command to gather facts of localhost using setup module
- Write Adhoc command to copy any file to suitable path of remote machine/vm whose IP specified in inventory present in the current directory 
  ```
    1. To override values in ansible.cfg for single usecase, copy ansible.cfg to current directory, configure absolute or relative path of inventory in ansible.cfg
    2. copy module in ansible
    3. learn to configure the connection from inventory, either connect remote machine by it's ssh username and passsweod or connect by private key of ssh account
  ```  
- Write a playbook to create a file in ansible on host machine (where ansible is running), which contain IP address of host machine all this in 1st play of the playbook and 2nd play should copy this file from this host machine to remote machine
```
1. check ansible_connection = local // for faster connection on localhost
2. explore remote_src option of copy module
```
- explore and use following frequently used modules from official Ansible doc
  - copy
  - Synopsis
  - file
  - lineinfile
  - fetch
  - path
  - package
  - uri
  - shell/command

## Flow control in playbook
-   



## Way to Implement large Automation
- [Roles](https://docs.ansible.com/ansible/latest/user_guide/playbooks_reuse_roles.html)
- [Collections](https://docs.ansible.com/ansible/latest/user_guide/collections_using.html)
- [Ansible Galaxy](https://docs.ansible.com/ansible/latest/galaxy/user_guide.html)

## Ansible GUI 
- [what is ansible tower](https://www.ansible.com/products/tower)
- [Ansible tower and AWX](https://www.redhat.com/en/resources/awx-and-ansible-tower-datasheet)


## References
- https://docs.ansible.com/
- https://medium.com/@me.sanjeev3d/ansible-configuration-management-945b56eed6d7
- https://github.com/ansible/ansible-examples
- https://docs.ansible.com/ansible/2.4/intro_configuration.html
- https://docs.ansible.com/ansible/latest/dev_guide/overview_architecture.html
- https://docs.ansible.com/ansible/latest/cli/ansible.html


