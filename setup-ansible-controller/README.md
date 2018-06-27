# Apigee OPDK Setup Ansible Controller Workspace

This folder contains the playbooks that uses the [Apigee OPDK Setup Ansible Controller](https://github.com/carlosfrias/apigee-opdk-setup-ansible-controller) 
role. An Ansible controller is used to run Ansible playbooks. This `setup.yml` script enables you to setup 
Ansible as a controller for setting up a local planet or the structure to manage multiple planets.

Please see [Apigee OPDK Setup Ansible Controller](https://github.com/carlosfrias/apigee-opdk-setup-ansible-controller) 
for additional details.

# Usage Instructions

## Sample Usage to Setup an Ansible Control Server in the local folder 

A basic controller can be configured in the current directory: 

    # Set the Ansible roles path to the current directory temporarily
    export ANSIBLE_ROLES_PATH=.
    
    # Download the required roles to setup the Ansible controller
    ansible-galaxy install -r setup-control-server-requirements.yml.yml  -f
    
    # Setup the Ansible controller
    ansible-playbook setup-control-server.yml -e remote_user=<remote user login> -e target_hosts=127.0.0.1 --connection=local

## Sample Usage to Setup an Ansible Control Server in a remote server 

A basic controller can be configured in the current directory: 

    # Set the Ansible roles path to the current directory temporarily
    export ANSIBLE_ROLES_PATH=.
    export ANSIBLE_LIBRARY=library
    
    # Download the required roles to setup the Ansible controller
    ansible-galaxy install -r setup-control-server-requirements.yml.yml  -f
    
    # Setup the Ansible controller
    ansible-playbook setup-control-server.yml -e remote_user=<remote user login> -e target_hosts=<ip address> 
    
### Change the location of the Ansible working folder
   
    # Set the Ansible roles path to the current directory temporarily
    export ANSIBLE_ROLES_PATH=.
    export ANSIBLE_LIBRARY=library
    
    # Download the required roles to setup the Ansible controller
    ansible-galaxy install -r setup-control-server-requirements.yml.yml -f
    
    # Setup the Ansible controller
    ansible-playbook setup-control-server.yml -e remote_user=<remote user login> -e ansible_workspace=~/.ansible
    
### Change the location of the Apigee configuration folder
   
    # Set the Ansible roles path to the current directory temporarily
    export ANSIBLE_ROLES_PATH=.
    export ANSIBLE_LIBRARY=library
    
    # Download the required roles to setup the Ansible controller
    ansible-galaxy install -r setup-control-server-requirements.yml.yml -f
    
    # Setup the Ansible controller
    ansible-playbook setup-control-server.yml -e remote_user=<remote user login> -e apigee_config_folder=~/.apigee
    
## Sample Usage to Backup an Ansible Control Server

    # Download the required roles to setup the Ansible controller
    ansible-galaxy install -r backup-control-server-requirements.yml.yml -f
    
    # Setup the Ansible controller
    ansible-playbook backup-control-server.yml -e target_hosts=<ip address of control server>
    
   

