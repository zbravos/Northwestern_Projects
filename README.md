## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

www.github.com/zbravos/Northwestern_Projects/Project1Diagram

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the Ansible Configuration file may be used to install only certain pieces of it, such as Filebeat.

www.github.com/zbravos/Northwestern_Projects/AnsibleConfigFiles.docx

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly distributed, in addition to restricting access to the network.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the data and system applications.

The configuration details of each machine may be found below.

| Name     | Function  | IP Address   | Operating System |
|----------|---------- |--------------|------------------|
| Jump Box | Gateway   |20.55.56.151  | Linux            |
| Web-1    |Web traffic|10.0.0.5      | Linux            |
| Web-2    |Web traffic|10.0.0.6      | Linux            |
| DVWA-VM3 |Web traffic|10.0.0.7      | Linux            |
|Elk-Server|Monitoring |137.135.53.229| Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
67.176.252.11

Machines within the network can only be accessed by the Jump Box VM, 20.55.56.151

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 67.176.252.11        |
| Web-1    | No                  | 20.55.56.151         |
| Web-2    | No                  | 20.55.56.151         |
|DVWA-VM3  | No                  | 20.55.56.151         |
|DVWA-VM4  | No                  | 20.55.56.151         |
|Elk-Server| No                  | 20.55.56.151         |


### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because it’s considerably faster and can be used to configure multiple machines at once.

The playbook implements the following tasks:
- Use more memory
-Install docker.io
-Install pip3
-Install docker python module
-Download and launch a docker web container
-Enable docker service

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

www.github.com/zbravos/Northwestern_Projects/ElkContainer.png

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
137.135.53.229


We have installed the following Beats on these machines:
Filebeat, Metricbeat

These Beats allow us to collect the following information from each machine:
Filebeat collects and tracks logging data, which can be used to track when new files are added or when changes to files have been made.
Metricbeat collects monitors OS and service data, which can be used to track updates, crashes, etc.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the Ansible Config file to a running container.
- Update the config file to include your VM’s IP
- Run the playbook, and navigate to your VM to check that the installation worked as expected.


