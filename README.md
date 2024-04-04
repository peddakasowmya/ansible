# ansible

# ANSIBLE
- Ansible is opensource, agent less, 
- purely works based on SSH
- works with push and pull commands
- The only thing you need to do that your ANSIBLE Server should be able to SSH to the nodes that need configuration management.

### ANSIBLE can be operated in 2 ways
    - Manual way        ( No code approach and its 100% not recommended)
    - Automated way     ( YAML : playbooks )

### Install ANSIBLE 
curl https://gitlab.com/thecloudcareers/opensource/-/raw/master/lab-tools/ansible/install.sh | sudo bash

To ansible, we need to supply the list of servers that needs to be amanaged by ANSIBLE and we cll tha file as INVENTORY FILE

    Inventory file
    Destination Server Username and Password


### Ansible is all about module

ansible all -i inventory -e ansible_user=centos -e ansible_password=DevOps321 -m shell -a "df -h"
ansible all -i inventory -e ansible_user=centos -e ansible_password=DevOps321 -m shell -a uptime

Using this approach we can run only 1 command at a time.

Automated way of dealing with ANSIBLE is with PAYBOOKS. Playbooks can be writted using YAML.

### LEARNING YAML:

     1) Dictionary      -- key with value
     2) List            -- key with multiple values
     3) Map             -- key with multiple key pairs

### YAML is indentation specific, that means spaces matters a lot.
    A key with a value is called                Dictionary
        name: ansible
    A key with multiple values is called as     List
        Courses:
            - devops
            - cloud
            - kubernetes
    A key with multiple key value pairs is called as    Map
        martin:
            name: Martin D'vloper
            job: Developer
            skill: Elite

# What is a PLAYBOOK  "Playbook - plays - tasks"
    ''' scripts in ansible are referred as playbook  '''  Playbook - plays - tasks

A playbook is a list of plays!!!
A play is a list of tasks!!!
A task is nothing an aciton that you want ansible to perform

Ansible expected the playbooks to have .yaml or yml as extensions

