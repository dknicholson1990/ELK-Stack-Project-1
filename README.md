# ELK-Stack-Project-1
The first cybersecurity project detailing the creation, install, and setup of an ELK stack VM Network.
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

https://github.com/dknicholson1990/ELK-Stack-Project-1/blob/main/Diagrams/ELK%20UPDATE.drawio.png

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

 https://github.com/dknicholson1990/ELK-Stack-Project-1/blob/main/Ansible/ansible%20playbook.txt

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly _____, in addition to restricting _____ to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system _____.
- _TODO: What does Filebeat watch for?_
- _TODO: What does Metricbeat record?_

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.4   | Linux            |
| Web-1    | DVWA/Beat| 10.0.0.5   | Linux            |
| Web-2    | DVWA/Beat| 10.0.0.6   | Linux            |
| ELK      | Monitor  | 10.1.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- 75.190.236.107

Machines within the network can only be accessed by _____.
-75.190.236.107

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 75.190.236.107       |
| Elk      | Yes                 | 75.190.236.107       |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- Ease of access as well as deployability, If new Virtual Machines need to be added the Deployment takes minutes.

The playbook implements the following tasks:
- Install the docker container to new vm
- Start install playbook to initialize ELK install and setup
- Install Filebeat for Logs
- Install Metricbeat for Metric data and monitoring


The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

https://github.com/dknicholson1990/ELK-Stack-Project-1/blob/main/Ansible/docker%20ps.png

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- 10.0.0.5
- 10.0.0.6

We have installed the following Beats on these machines:
-FileBeat
Metricbeat

These Beats allow us to collect the following information from each machine:
-Filebeat collects log information. This allows you to research, catagorize and evaluate specific information down to the day and time of your choice.
-Metricbeat is used to collect and ship operating system and service metrics to one or more destinations. This allows you to see how the system is running and what is using the most or least resources.
### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_ The playbook files are always in .yml format. and you can copy form the host machine to the virtual machine.
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_ You will need to makesure in the .yml file you have the machine specified in the HOSTS section. You will make a seperate playbook and specify the hosts machine.
- _Which URL do you navigate to in order to check that the ELK server is running? http://[your.VM.IP]:5601/app/kibana

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
ssh jumpbox@ ip address
start and attach container
curl (git clone location of updated files)
cd /etc/ansible
nano hosts (add vms ip to webserver and new section ELK for elk vm)
nano ansible.conf to add the remote user to server
   
