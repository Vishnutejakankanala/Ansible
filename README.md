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

**Build communication between two servers/VM's** 
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

cd /etc/ansible   :- It is a default path of ansible.

Create **hosts** file to store IP address and [name of Operating Systems] Ex:- ubuntu, centeos.

Create a **Playbooks** directory. Then, start writing a files and execute them. ex:- nginx.yaml, tasks.yaml creat.yaml and etc.

Playbook files are written in a .YAML files. Use **sudo** to edit the files.

ansible-playbook <file name> --syntax-check   :- to check sntax is correct or error

ansible-playbook <file name>   :- To execute yaml file.

**Ansible adhoc Command**
````
Ad hoc commands are one-off commands that are executed on the command line of an Ansible control node,
without the need for a playbook or any additional configuration.
These commands are used to quickly perform tasks on one or more managed nodes,
such as checking the status of a service or installing a package.

ansible -i hosts <ipadress> -m "shell" -a "touch <file>" :- To create file in target machine
ansible -i hosts <ipadress> -m "shell" -a "ls -la" :- To list all files and folders in target VM
````
# Ansible-galaxy Command
Jump-start your automation project with great content from the Ansible community. Galaxy provides pre-packaged units of workflows. such as roles and collections.
 It includes multiple playbooks, roles, modules and plugins.



