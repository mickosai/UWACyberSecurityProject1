# UWACyberSecurityProject1
Project 1 - Elk Stack


Automated ELK Stack Deployment
The files in this repository were used to configure the network depicted below.

Diagram

![image](https://user-images.githubusercontent.com/72793957/117332763-ce239f80-aeca-11eb-8f45-8ee43bfdc27b.png)



These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the playbook file may be used to install only certain pieces of it, such as Filebeat.

filebeat-playbook.yml

This document contains the following details:

Description of the Topology
Access Policies
ELK Configuration
Beats in Use
Machines Being Monitored
How to Use the Ansible Build
Description of the Topology
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting access to the network.

Load balancers protect the servers from a denial of service attack. A load balancer distributes traffic amongst the servers. One benefit of using a jump box is that it protects your virtual machines from publix exposure.
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the log files and system performance.

log files monitored by Filebeat
The configuration details of each machine may be found below.

![image](https://user-images.githubusercontent.com/72793957/117333535-99fcae80-aecb-11eb-9100-d41ec47ded2b.png)


Access Policies
The machines on the internal network are not exposed to the public Internet.

Only the Jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:

72.84.225.151
Machines within the network can only be accessed by Port 22.

10.0.1.4
A summary of the access policies in place can be found in the table below.

![image](https://user-images.githubusercontent.com/72793957/117333587-a97bf780-aecb-11eb-82b0-1207d57e65ef.png)

Elk Configuration
Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...

Ansible can be run from the command line and will ensure our provisioning scripts run identically everywhere.
The playbook implements the following tasks:

Change the memory on the ELK VM
Install docker.io
Install python-pip
Install docker python module
Download and launch a docker elk stack
The following screenshot displays the result of running docker ps after successfully configuring the ELK instance.

Sebp/Elk Running

Target Machines & Beats
This ELK server is configured to monitor the following machines:

10.0.1.7
10.0.1.8
10.0.1.9
10.0.1.10
We have installed the following Beat on these machines:

filebeat-7.6.1-amd64.deb
This Beat allow us to collect the following information from each machine:

Filebeat is used to send your log files to kibana. Filebeat monitors and collects log events on specificed servers.
Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:

SSH into the control node and follow the steps below:

Copy the Filebeat-configuration.yml file to the ELK VM.
Update the hosts file to include webservers 10.0.1.7, 10.0.1.8, 10.0.1.9, 10.0.1.10
Run the playbook, and navigate to Kibana to check that the installation worked as expected.

![image](https://user-images.githubusercontent.com/72793957/117333684-c1ec1200-aecb-11eb-8b83-6b27a4507b87.png)
