ansible-galaxy role install bsmeding.swag_docker : command used to pull and install roles form ansible galaxy website
ll ~/.ansible/roles/  : To check the installed roles 

# write a file docker-playbook.yaml to install docker in target VM

```
- hosts: centos
  become: true
  roles:
    - bsmeding.swag_docker
```

run commands
ansible-playbook --syntaxc-check docker-playbook.yaml : To check yaml file is correct or not
ansible-playbook docker-playbook.yaml : To execute yaml file

in the target VM docker will install
use "Docker" command to check

# adding roles to ansible
ansible-galaxy role init httpd : to create httpd role 
