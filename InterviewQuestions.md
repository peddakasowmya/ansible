# Ansible Interview Questions

1) Why ansible is famouse and list me 3 points on why do I need to adopt ?

2) What is the default ansible mechanism ?

3) If you're asked to decided on the usage of Pull vs Push, what would you select and would be the factors that determine the usage ?

4) Assume your infra is dynamic that scales out & in dynamically and in this case, would you prefer to use push or pull ?

5) What is the need of ROLES in ansible ?

6) If the values of the variables are declared both in vars/main.yml and default/main.yml, which among these will have priority ?

7) What is the eariest way to organize the varaibles in files based on the environment ? Can we supply the vairablesin files ?

8) How to call a role from another rle using the task name ?

9) What all modules have you used in Ansible and which version of ansible are you using ?

10) What is the notify keyword in Ansible? Scenario, I want to make sure that service should only be restarted if there is a change in the file, how can you accomplish that ?

11) What is ROLE DEPENDENCY and what's the purpose of it and when to use that ?

12) What is the purpose of the become directive in Ansible? Can we run a playbook with 5 tasks as a root user and x-task in that 5 tasks as centos user 

13) What's the purpose of rescue module and when do you use that ?

14) Situation, if any of the 3 tasks in a playbook fails then I would like to run 5 specific tasks on the 3 tasks failure, how can we deal that ?

15) What is a BLOCK in ansible ?

16) How can we extract a specific string consider a password from a file that's available on a remote host 

17) What's the main purpose of SLURP function in ansible ?

18) What is the different between collections vs module ?

19) How can we control the facts not to be collected by Ansible Controller ?

20) What is the port number used by ansible ?

21) What are the packages that needs to be installed on remote nodes that needs to be controlled by ansible ?

22) Why ansible is referred as AGENT-lESS

23) If there are any sensitive pieces of information on your playbook like API Tokens, what's the strategy that you would follow to encrypt them ?

24) How can extract all the facts gather by ANSIBLE ?

25) How do you manage package installations using Ansible?

26) What is the difference between register and set_fact? When to use what ?

27) How do you loop over items in Ansible? 

28) How do you handle errors in Ansible playbooks? 
    ``` Use ignore_errors or failed_when to manage task failures.```

29) What is an inventory file in ansible ?

30) When to use ansible vs ansible-playbook vs ansible-pull ?

31) If your playbook is on DRIVE, can you run it using ansible-pull ?

32) What are the pre-requisites for ansible to operate using ansible-pull 

33) How does Ansible differ from other configuration management tools like Puppet or Chef?

    * Ansible is agentless, meaning it doesn’t require any agents on managed nodes.
    * It uses YAML-based playbooks for defining tasks.
    * Ansible is easy to learn and doesn’t require a master-agent architecture.

34) What is the difference between list vs dictionary vs map object in YAML ?

35) How can you leverage Ansible Vault to manage secrets for different environments (e.g., dev, test, prod)?

36) Can we use ANSIBLE to create infrastructure on cloud ? If yes, why it's not at all preferred

37) How can you achieve variable precedence and inheritance in Ansible?

38) Discuss different ways to manage complex data structures (e.g., loops, conditionals) within Ansible playbooks. What are the conditions that you've used in ansible ?

39) Explain me how would you handle this situation, If you have 300 vm's ( Combined ) of Redhat Linux,7,8,9 and ubuntu 18,20,22. Due to the security findings, you were asked to patch the package xyz on all the Redhat 9 machines of the inventory that you have, how can you do that ?

40) Scenario : You have 500+ VM's and you would like to restart all the VM's whose uptime is greater than 100 days

41) Scenario: You need to deploy a complex application with dependencies between different servers. How would you model this in your Ansible playbooks using handlers ?

42) How would you configure secure access for your Ansible control node using SSH key management?

43) Explain best practices for managing secrets and sensitive data within Ansible playbooks using Ansible Vault.

44) How to run the playbook on debug mode 