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
sudo git init : To initialize git
sudo git remote add  origin https://github.com/Vishnutejakankanala/Ansible : 
sudo git remote -v :
sudo git add . :
sudo git commit -m "first files" : 
if required run
sudo git config user.email "vishnutejakankanala9@gmail.com" : your mailid
sudo git config user.name "Vishnu Teja Kankanala" : your name
sudo git branch -M main : to change master branch to main
sudo git push -u origin main : to push to github
ansible-galaxy import Vishnutejakankanala Ansible -token <ansible-galaxy token in website> : To get import request & repo will create in ansible-galaxy roles in website


git token : 
sudo git branch : To check you are in which branch
sudo git branch -a : To check how many branches are available in local and remote
