# Deploying a Node Js Application on AWS EC2 with Ansible Automation

# Deploying remote Nginx Server which hosts a static HTML website on AWS Linux (EC2) using Automation (Ansible)
### DESCRIPTION

#### PROJECT IDEA

I came across a DevOps project: "Deploying Node JS application on AWS EC2" by Kunal Verma 
In this project, we deploy Node JS application on AWS EC2 Ubuntu instance, Themanual steps can be found here: https://github.com/verma-kunal/AWS-Session .

The DevOps Engineer in me saw an opportunity to add automation to it, so I used Ansible to deploy this application on AWS with a single command.
This project will help you with these job requirements :


- Provision and configure infrastructure through automation
- Required experience in Configuration Management tools (eg PowerShell, Bash, etc)
- Understanding of web application development, server deployment and upkeep, and general networking practices.


###  ENVIRONMENT

**Host & Remote Nodes**: AWS Ubuntu EC2
**Application**: Node JS Application
**Automation**:  Ansible

I chose AWS for making remote machines because it spins up instances in seconds with the EC2 service & interacting with the environment becomes super easy.
SSH communications is the key for deploying via Ansible. It is agent-less i.e you don't need to install it on remote machines


### CHALLENGES FACED


- Creating the network & SSH between the 2 machines (Host & Remote Node).

- Ansible playbook modules and configuration.

- Facing continuous errors at most of the steps & troubleshooting them ( That's what is the most important & toughest part of the project).

### BUILDING THE PROJECT

#### ANSIBLE INSTALLATION ON HOST NODE
Follow this video:https://www.youtube.com/watch?v=UIaK9yZiuP0
#### SETTING UP EC2 , Establishing SSH connection between server & Node
![image](https://github.com/dv-sharma/NodeJSDeploy/assets/65087388/c44b69f3-c335-40b6-85b6-d18f02926009)

INSTANCE LOGIN COMMAND: 
```
ansible-playbook -i /etc/ansible/hosts -u ubuntu playbook1.yml
```

x
#### ENTRY OF REMOTE INSTANCE IN /ETC/ANSIBLE/HOSTS 
[servers]
server1 ansible_host=172.31.86.197

#### CREATION OF ANSIBLE PLAYBOOK : playbook1.yml
#### DEPLOYING THE ANSIBLE PLAYBOOK
Command: 
```
ansible-playbook -i /etc/ansible/hosts -u ubuntu playbook1.yml
```

#### ACCESSING THE APPLICATION AT REMOTE HOST PUBLICIP:PORT
Make sure to add the port you configured in .env file in the security group attached to the instance

![image](https://github.com/dv-sharma/NodeJSDeploy/assets/65087388/15115842-49ee-44c8-a759-6705914f4d17)

#### Application deployed with playbook and accessible through instance IP and port 🎉
![image](https://github.com/dv-sharma/NodeJSDeploy/assets/65087388/a3ee68b1-bcfa-480f-8548-848501c91e54)


