# ansible
### JENKINS credentials
admin
Password


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

###### https://docs.ansible.com/ansible/latest/reference_appendices/YAMLSyntax.html

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
A task is nothing but an aciton that you want ansible to perform

Ansible expected the playbooks to have .yaml or yml as extensions


### HOW TO RUN A PLAYBOOK       ?

    ''' $ ansible-playbook -i inventory -e ansible_user=centos -e ansible_password=DevOps321 pbname.yaml'''
ansible-playbook -i inventory -e ansible_user=centos -e ansible_password=DevOps321 001-playbook.yaml


### Roles in Ansible
 Roles let you automatically load related vars, files, tasks, handlers, and other Ansible artifacts based on a known file structure. After you group your content into roles, you can easily reuse them and share them with other users.

The advantage of using ROLES is code re-usability and things will be dry.


roles/
    common/               # this hierarchy represents a "role"
        tasks/            #
            main.yml      #  <-- tasks file can include smaller files if warranted
        handlers/         #
            main.yml      #  <-- handlers file
        templates/        #  <-- files for use with the template resource
            ntp.conf.j2   #  <------- templates end in .j2
        files/            #
            bar.txt       #  <-- files for use with the copy resource
            foo.sh        #  <-- script files for use with the script resource
        vars/             #
            main.yml      #  <-- variables associated with this role
        defaults/         #
            main.yml      #  <-- default lower priority variables for this role
        meta/             #
            main.yml      #  <-- role dependencies


# Commands to run the Roboshop project:
frontend: 
gp ; ansible-playbook -i inv-dev -e ansible_user=centos -e ansible_password=DevOps321 -e COMPONENT=frontend -e ENV=dev roboshop.yml

Mongodb:
gp ; ansible-playbook -i inv-dev -e ansible_user=centos -e ansible_password=DevOps321 -e COMPONENT=mongodb -e ENV=dev roboshop.yml

catalogue:
gp ; ansible-playbook -i inv-dev -e ansible_user=centos -e ansible_password=DevOps321 -e COMPONENT=catalogue -e ENV=dev roboshop.yml

redis:
gp ; ansible-playbook -i inv-dev -e ansible_user=centos -e ansible_password=DevOps321 -e COMPONENT=redis -e ENV=dev roboshop.yml

User:
gp ; ansible-playbook -i inv-dev -e ansible_user=centos -e ansible_password=DevOps321 -e COMPONENT=user -e ENV=dev roboshop.yml

cart:
gp ; ansible-playbook -i inv-dev -e ansible_user=centos -e ansible_password=DevOps321 -e COMPONENT=cart -e ENV=dev roboshop.yml

mySQL:
gp ; ansible-playbook -i inv-dev -e ansible_user=centos -e ansible_password=DevOps321 -e COMPONENT=mysql -e ENV=dev -e MYSQL_PSW=RoboShop@1 roboshop.yml

Shipping:
gp ; ansible-playbook -i inv-dev -e ansible_user=centos -e ansible_password=DevOps321 -e COMPONENT=shipping -e ENV=dev roboshop.yml

RabbitMQ:
gp ; ansible-playbook -i inv-dev -e ansible_user=centos -e ansible_password=DevOps321 -e COMPONENT=rabbitmq -e ENV=dev roboshop.yml

Payment:
gp ; ansible-playbook -i inv-dev -e ansible_user=centos -e ansible_password=DevOps321 -e COMPONENT=payment -e ENV=dev roboshop.yml




# Ensure you have 
* sudo dnf install mysql-devel -y
* sudo pip3 install mysqlclient


# When to use PUSH and PULL Mechanisms ?

    1) Push Mechanism Is Used, if your inventory is STATIC ( typically on-prem ) or wher is not concept of scaling, then you can use PUSH. Because your intentory maintenance is a one time job.  

    2) Pull Mechanism Is User, if your inventory is dynamic that means servers would be coming up and down as a part of the SCALE OUT & SCALE IN Policies.

       * In Pull Based Mechanism, the expectation is that when a server is provisioned, CM should also be coming up as a part of the startup
       * For pull based mechanism, ensure the server should have the ansible Installed. 
       * Ansible Installation can be done either by 

                1) Placing the ANSIBLE Installation Script as a part of the system start up 
                2) Ensure the AMI that you're using for your server creation should have Ansible Installed 
                3) As of today, ansible-pull can only fetch the code from GIT based repositories only


### We can enter this in advanced section while creating the srever, as this will be executed at the time of execution.
ex:
 curl https://gitlab.com/thecloudcareers/opensource/-/raw/master/lab-tools/ansible/install.sh | sudo bash   