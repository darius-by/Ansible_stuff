# Ansible_stuff

# This readme provides a step by step guide how to create an ansible playbook to create users, 
# remove default "ubuntu" user, add new users to sudo group, upload ssh keys and allow users to run sudo commands 
# without a password on Ubuntu virtual machine in AWS.

# Firstly Ansible should be setup on a local machine.

# In a terminall app run:

pip install ansible 

# Next, generate ssh key pair for a user on a local machine, run:

ssh-keygen -t rsa

# Next, create ansible configuration file "ansible.cfg" and inventory file "hosts" in /etc/ansible
# Configuration file will store default values for ansible to work with and host file will contain IP addresses of all remote hosts.

# Inside ansible.cfg write the following and save:

[defaults]
inventory = hosts
remote_user = dariusbyckovskij
private_key_file = ~/.ssh/id_rsa

# Inside hosts file write the following and save:

[main]

18.184.88.141

[main:vars]
sshd_use_pam=no
sshd_password_authentication=no
sshd_permitroot=no

