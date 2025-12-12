<<<<<<< HEAD
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



=======
Role Name
=========

A brief description of the role goes here.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
>>>>>>> b57b6f4 (first files)
