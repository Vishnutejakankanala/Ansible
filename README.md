# Ansible
**Installation of ansible on VM**
````
Create a two Vm's on ec2 instance one is ansible-server and other is Target-Machine
sudo hostnamectl set-hostname <newhostname>     :- Tochange the hostname (ansible-server or Target-vm)
ansible --version         :- To check ansible installed or not
sudo yum install ansible  :- To install ansible on linux
sudo apt install ansible  :- To install ansible on ubuntu
ansible centos -m ping    :- To check target machine reaching or not.
````

**Build communication on two servers/VM's** 
````
ll -a /home/ec2-user/.ssh   :- To find .ssh folder
ssh-keygen -t rsa           :- To generate or create ssh keys
You can find id_rsa & id_rsa.pub files in .ssh folder.
sudo nano ansible.pem       :- To copy loacal public to remote
sudo cp <ansible.pem> <ansible.pem.pub> :- To copy public id in .pub file
ssh-copy-id -i ~/.ssh/id_rsa.pub ec2-user@<target-vm public ip> :- To copy public ssh key to target vm
cat /home/ec2-user/.ssh/id_rsa.pub :- copy ssh key and past in target VM
sudo nano .ssh/authorized_keys     :- Do it in target VM and past id_rsa.pub file.
ansible centos -m ping             :- To check target machine reaching or not on ansible server
````


cd /etc/ansible   :- It is a default path of ansible
Create **hosts** file to store IP address and [name of Operating Systems] Ex:- ubuntu, centeos
Create a **Playbooks** directory. Then, start writing a files and execute them.

Playbook files are written in a .YAML files

ansible-playbook <file name> --syntax-check   :- to check sntax is correct or error

ansible-playbook <file name>   :- To execute yaml file.
