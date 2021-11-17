# BSL-Cloud-Automation-Workshop
This Gudance is about Ansible Configuration Management on AWS Cloud (EC2 Instance) to configure nginx webserver.

#Prerequisite:
1. Create AWS Account
2. Spin up a new EC2 Instance using AMI2 distrubution
3. Enable ssh service (port 22/tcp) from any source via AWS Security Group attached with EC2 instance created above.
4. Enable Password Authentication of each instance (/etc/ssh/sshd_config)
    PasswordAuthentication yes
    systemctl restart sshd

#Local setup with SSH authentications:
1. Create ssh keys on Control Node (from ec2-user)
    ssh-keygen

2. Copy ssh key (public key) to manage nodes (as ec2-user)
    ssh-copy-id ec2-user@instance-ip

#Ansible Installation:
1. Install Ansible
2. Add IP Address of Manage nodes into following files.
    ansible/inventory
    ansible/roles/deploy_nginx/test/inventory
    
#Execute Ansible Playbook
1. Run "install_repo_update.yml" to install packages and update packages

2. Run "playbook.yml" to run nginx deployment
