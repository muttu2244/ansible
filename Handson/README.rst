Ansible Training

1) YAML Basics
2) AdHoc Ansible Commands
3) Ansible Playbooks (Name, hosts/groups, Vars, Tasks, handlers, service,
4) Ansible Roles
5) Ansible Inventories
6) Ansible Modules
7) Templating with Jinga2
8) AWS with Ansible
9) Docker support with Ansible
10) Ansible with Python


-------------------------------------------------------------------------------

PreRequisites
-----------------------
A) Create a new Amazon Instance in AWS (EC2) in the Mumbai Region
    enable SSH(port 22) and HTTP (port80) in INBOUND Rules in the Security Group
    Create a new Key pair or use existing key (download .pem file)
    Launch the instance




Installing Ansible on Ubuntu (on windows)
Note: we can also use Cygwin to install ansible on windows

1) Create a AnsibleExamples folder
2) Create a virtualenv inside it
      pip install virtualenv
      virtualenv env
      source env/bin/activate
      which python
      pip list
3) Install Git
      sudo apt-get install git
4) Install Ansible
      pip install git+https://github.com/ansible/ansible

5) upgrade pip (if you get any errors in the above installation)
      pip install --upgrade pip

6) update python libraries (if you get any errors in the above installation)
      sudo apt-get install python-dev

7) pip freeze (to check all the dependencies installed)

8) Run "ansible --version" to check if it has installed successfully

9) Run "ansible all -i localhost, -c local -m ping"
    (Notes:
          leave a space after ","
          "-i" is for localhost inventory
          "-c" is for local connection
          "-m" is for ping module
    )

-------------------------------------------------------------------------------





1) Create a EC2 instance , Add "SSH" Inbound Traffice in the Security Group
2) Give full permissions to "ansible3.pem" file to make it work ("sudo chmod 777 ansible3.pem")
3) Run the script "Access_Machine.py" from the ubuntu on windows machine with sudo user

        Ex1:
            Run

            "cd /mnt/d/AnsibleExamples/ansible_hands_on_training-develop/ansible_tutorial_cli/"
            "python3 access_machine.py" (Note : Use "python3" )

        "ssh -i /mnt/d/AnsibleExamples/ansible3.pem ec2-user@13.127.58.182"

4)

    Ex 2:

        "python auto_update_machine.py"  ( Note : use "python" and not "python3" (no configParser))

        Command to execute:
        ssh -i /mnt/d/Miscellaneous/ansible1/ansible3.pem ec2-user@13.127.58.182 -t 'sudo yum update -y'


5) Command to execute:

    ansible webservers -a "sudo yum update -y"
    ansible webservers -v -a "sudo yum update -y"


Note: "/etc/ansible/ansible.cfg " and "/etc/ansible/hosts" are the default files used by Ansible , they do not use the cfg files
or hosts files from the current working directory becuase of the following...

https://docs.ansible.com/ansible/latest/installation_guide/intro_configuration.html
https://docs.ansible.com/ansible/latest/reference_appendices/config.html#ansible-configuration-settings


6) ansible-playbook playbook_0100.yml
7)

