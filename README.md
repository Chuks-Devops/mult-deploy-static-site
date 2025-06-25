## Ansible Static Site Deployment

This project automates the deployment of static sites using NGINX on both Ubuntu and Amazon Linux systems. It configures the server, installs NGINX, downloads site files from url then move the file to nginx html folder, and ensures idempotent and repeatable deployment.

## Features
- Supports Ubuntu and Amazon Linux.

- Auto-installs and configures NGINX.

- Deploys static site files from local or remote sources.

- Supports multi-environment inventories (prod, dev).

## Prerequisites
- Ansible >= 2.10

- Python 3.x

- SSH access to target servers

- Inventory of target hosts

## Install ansible on ubuntu
```
sudo apt update && sudo apt upgrade -y
sudo apt install software-properties-common

sudo add-apt-repository --yes --update ppa:ansible/ansible

#Install Ansible
sudo apt install ansible -y

#Validate Ansible:
ansible ---version

```

## Install python3 and pip on CentOS:
```
Sudo yum install epel-release
Sudo yum install python3-pip
```

#Install python3 and pip on RHEL:
```
sudo dnf install --assumeyes python3-pip

#Install python3 and pip on MacOS:
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
brew install python

#Install python3 and pip on Ubuntu:
sudo apt update
sudo apt install python3-pip

#Install python3 and pip on Windows: 

Run the Python installer for Windows and select "Add Python 3.x to PATH", this will ensure pip is callable from cmd.

#Validate you have python and pip installed:
Python3 ---version
pip ---version

#Install Ansible using pip:
pip install ansible
 
#Validate Ansible
Ansible ---version
```

## Setup

```
git clone https://github.com/Chuks-Devops/mult-deploy-static-site.git
cd mult-deploy-static-site
```

##  Inventory Setup
```
webapp01 ansible_host=<ip-address> ansible_user=ec2-user ansible_ssh_private_key_file=ansible.pem
webapp02 ansible_host=<ip-address> ansible_user=ec2-user ansible_ssh_private_key_file=ansible.pem
```


## Execute ansible playbook
```
ansible-playbook -i inventory main.yaml
```