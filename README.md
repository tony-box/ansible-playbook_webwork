This is an Ansible playbook that will deploy [WeBWorK](http://webwork.maa.org/) into AWS EC2 instances.

## Before you start
1) You must already have an AMI configured that allows your Ansible server to connect and assume a role with the proper permissions.

2) The dynamic inventory must be configured ( ansible-playbook_webwork/inventories/dev/ec2.ini ) for each DEV|TST|PRD in order to deploy to the proper servers. Do so using tags within AWS for your EC2 instances. The defaults are tag:Environment=DEV|TST|PRD&tag:Application=Webwork

3) Ensure you go through all of the files within inventories/DEV|TST|PRD/group_vars/all and change all variables to your own values.

This playbook has been tested on:

- Ubuntu 16.04 
- WeBWorK 2.13
- RDS MySQL Database
- EFS mount for shared filestorage across servers
- Dedicated Rserver
