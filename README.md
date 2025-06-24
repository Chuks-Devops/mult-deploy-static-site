## Ansible Static Site Deployment
![Uploading Screenshot 2025-06-24 112939.png…]()


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
