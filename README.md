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

     1) Dictionary
     2) List
     3) Map

### YAML is indentation specific, that means spaces matters a lot.
    A key with a value is called                Dictionary
        name: ansible
    A key with multiple values is called as     List
    Courses:
        -devops
        -cloud
        kubernetes
    A