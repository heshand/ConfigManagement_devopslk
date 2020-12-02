# BSL-Cloud-Automation-Workshop
BSL Cloud Automation Workshop

1. Enable Password Authentication of each instance (/etc/ssh/sshd_config)
    PasswordAuthentication yes
    # systemctl restart sshd

2. Create ssh keys on Control Node (from ec2-user)
    # ssh-keygen

3. Copy ssh key (public key) to manage nodes (as ec2-user)
    # ssh-copy-id ec2-user@instance-ip

4. Add IP Address of Manage nodes into following files.
    ansible/inventory
    ansible/roles/deploy_nginx/test/inventory
    
5. Run "install_repo_update.yml" to install packages and update packages

6. Run "playbook.yml" to run nginx deployment
