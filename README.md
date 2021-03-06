# Ansible
Anyone who is interested in operating machines remotely, having basic knwledge of linux can follow these steps to learn Ansible, and perform interesting set of operations remotely.

## Contents
- [Introduction](#introduction)
- [Basic implementation](#basic-implementation)
- [Flow control in playbook](#flow-control-in-playbook)
- [Way to Implement large Automation](#way-to-implement-large-automation)
- [Ansible GUI](#ansible-gui)
- [Advance](#advance)
- [References](#references)

---- Let's Start ----------------------------------------------
## Introduction
-  [Ansible quickstart](https://docs.ansible.com/ansible/devel/user_guide/quickstart.html)
-  [YAML basics](https://www.tutorialspoint.com/ansible/ansible_yaml_basics.htm)
-  [Terminology](https://docs.ansible.com/ansible/devel/user_guide/basic_concepts.html)
-  [Installation](https://docs.ansible.com/ansible/latest/installation_guide/index.html)
-  [How ansible work](https://www.ansible.com/overview/how-ansible-works#:~:text=EFFICIENT%20ARCHITECTURE,and%20removes%20them%20when%20finished.)
-  [Getting started](https://docs.ansible.com/ansible/devel/user_guide/basic_concepts.html)
-  [First Innevtory](https://docs.ansible.com/ansible/devel/user_guide/intro_inventory.html)
-  [Ansible config file precedence](https://docs.ansible.com/ansible/latest/reference_appendices/config.html)


## Basic Implementation 

-  [Ad hoc commands](https://www.tutorialspoint.com/ansible/ansible_ad_hoc_commands.htm#:~:text=Ad%20hoc%20commands%20are%20commands,usr%2Fbin%2Fansible'.)
-  [Run first playbook](https://docs.ansible.com/ansible/latest/network/getting_started/first_playbook.html)
-  [Working with modules](https://docs.ansible.com/ansible/latest/user_guide/modules.html)
-  [Ansible connection](https://docs.ansible.com/ansible/latest/user_guide/connection_details.html)
-  [Register variables](https://www.linuxtopic.com/2019/02/ansible-registrar-variables.html)
-  [Ansible Vault](https://docs.ansible.com/ansible/latest/user_guide/vault.html)
-  [setup module to gather facts](https://docs.ansible.com/ansible/latest/modules/setup_module.html)
-  [Special variables](https://docs.ansible.com/ansible/latest/reference_appendices/special_variables.html)
-  [Ansible actions/Meta](https://docs.ansible.com/ansible/latest/modules/meta_module.html)


#### Assignnments
### Setup
- Require 2 vm in same network
- Install ansible on 1st (host vm)
- Make sure python is available on 2nd (remote vm)
- Setup text editor for ansible yaml (eg for vim add `autocmd FileType yaml setlocal ts=2 sts=2 sw=2 expandtab` in $HOME/.vimrc)
- Create two users ansible_password and ansible_key in remote vm (without granting sudo access) and make sure st user is accessavle by ssh username and password, and for 2nd user ansible_key generate a new public private key private key parir and try to login here by ssh using private key 
### Questions
- Write a adhoc command to gather facts of localhost using setup module and try to get specific value using filter attribute of setup module
- Write Adhoc command to copy any file to suitable path of remote machine/vm whose IP specified in inventory present in the current directory 
  ```
    1. To override values in ansible.cfg for single usecase, copy ansible.cfg to current directory, configure absolute or relative path of inventory in ansible.cfg
    . Learn to configure the connection from inventory, either connect remote machine by it's ssh username and passsweod or connect by private key of ssh account
  ```  
- Write a playbook to create a file in ansible on host machine (where ansible is running), which contain IP address of host machine all this in 1st play of the playbook and 2nd play should copy this file from this host machine to remote machine
```
1. Check ansible_connection = local // for faster connection on localhost
2. Explore remote_src option of copy module
```
- Explore and use following frequently used modules from official Ansible doc
  - debug
  - set_fact
  - copy
  - synchronize
  - file
  - lineinfile
  - fetch
  - path
  - package
  - uri
  - shell/command
  - service
  - add_host
  - user/group

## Manage Flow control and more
-  [conditionals](https://docs.ansible.com/ansible/latest/user_guide/playbooks_conditionals.html) 
-  [Looping](https://docs.ansible.com/ansible/latest/user_guide/playbooks_loops.html)
-  [Filters](https://docs.ansible.com/ansible/latest/user_guide/playbooks_filters.html)
-  [Task delegation](https://docs.ansible.com/ansible/latest/user_guide/playbooks_delegation.html)
-  [Include and Import](https://docs.ansible.com/ansible/latest/modules/include_module.html)
-  [privilege escalation](https://docs.ansible.com/ansible/latest/user_guide/become.html#using-become)
-  [Jinja templating](https://docs.ansible.com/ansible-container/container_yml/template.html)
-  [Input from console](https://docs.ansible.com/ansible/latest/user_guide/playbooks_prompts.html#:~:text=The%20user%20input%20is%20hidden,visible%20by%20setting%20private%3A%20no%20.&text=Prompts%20for%20individual%20vars_prompt%20variables,as%20cron%20or%20Ansible%20Tower)
#### Assignnment

```
1. (If 2 remote vm are available) You are running ansible on host machine 'say 'A', now write a playbook to create 5 different files (named 'a', 'b', 'c', 'd', 'e') on remote machine 'say B' and copy all this files to remote machine 'say C' directly from 'B' to 'C'. 
2. Write a playbook in ansible to install httpd or nginx on remote vm, 
  generate a index.html file which will be hosted later, 
  content of this file should be IP address and hostname of the remote vm (where file will be hosted), 
  copy this file on appropriate path of remote vm and start the service, 
  edit "etc/hosts" of host to access remote server with custom name, 
  check the status code of the newly hosted webpage using URI module get request. 
3. Copy a file from single host present in inventory group called "webserver" to remaining hosts mentioned in inventory in (under all other groups) 
```



## Way to Implement large Automation
- [Roles](https://docs.ansible.com/ansible/latest/user_guide/playbooks_reuse_roles.html)
- [Collections](https://docs.ansible.com/ansible/latest/user_guide/collections_using.html)
- [Ansible Galaxy](https://docs.ansible.com/ansible/latest/galaxy/user_guide.html)
- [Best Pratices](https://docs.ansible.com/ansible/latest/user_guide/playbooks_best_practices.html)

## Ansible GUI 
- [what is ansible tower](https://www.ansible.com/products/tower)
- [Ansible tower and AWX](https://www.redhat.com/en/resources/awx-and-ansible-tower-datasheet)
#### Assignnment
- deploy awx container and try to run playbook directly from git to any machine in local network 
```
Explore: inventory, projects, credentials(machine and vault), template(job and workflow), Jobs(logging)
```
# Advance
- [Host pattern](https://docs.ansible.com/ansible/latest/user_guide/intro_patterns.html)
- [Writting python logic in ansible](https://github.com/hmharsh/Ansible-important-features/blob/master/using%20python%20code%20in%20ansible.txt)
- [Custom modules](https://medium.com/@heenashree2010/create-a-custom-module-with-ansible-python-6285874a09b4#:~:text=Write%20your%20first%20python%20program&text=The%20testing.py%20module%20utility,%2C%20import%20from%20testing.py.&text=This%20will%20import%20all%20the,python%20file%20is%20only%20JSON), [more examples](https://github.com/hmharsh/Ansible-important-features/tree/master/custom_module) check existing moudule from configured path written in both python and powershell
- Dynamic inventory [Working](https://docs.ansible.com/ansible/latest/user_guide/intro_dynamic_inventory.html), [Development](https://docs.ansible.com/ansible/latest/dev_guide/developing_inventory.html) 
- [Data Manipulation](https://medium.com/opsops/data-manipulation-in-ansible-json-query-769fb34655d4)
- Testing framework in ansible [Molecule](https://molecule.readthedocs.io/en/latest/)
- Connect remote windows host [doc](https://docs.ansible.com/ansible/latest/user_guide/windows_setup.html), [add_host](https://github.com/hmharsh/Ansible-important-features/blob/master/add%20host.txt)
## References
- https://docs.ansible.com/
- https://medium.com/@me.sanjeev3d/ansible-configuration-management-945b56eed6d7
- https://github.com/ansible/ansible-examples
- https://docs.ansible.com/ansible/2.4/intro_configuration.html
- https://docs.ansible.com/ansible/latest/dev_guide/overview_architecture.html
- https://docs.ansible.com/ansible/latest/cli/ansible.html


