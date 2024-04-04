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

