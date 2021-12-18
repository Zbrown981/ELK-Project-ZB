# ELK-Project-ZB
ELK Project Documentation 
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

(Images/Docker-ps.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Enter the playbook file._

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting access to the network.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the servers and system logs.

The configuration details of each machine may be found below.

-══════════════════════-═══════════-═════════════-══════════════════-
║                Name  ║ Function  ║ IP Address  ║ Operating System ║
-══════════════════════-═══════════-═════════════-══════════════════-
║ Jump-Box-Provisioner ║ Gateway   ║ 10.0.0.4    ║ Linux            ║
-══════════════════════-═══════════-═════════════-══════════════════-
║ Web1                 ║ Server    ║ 10.0.0.5    ║ Linux            ║
-══════════════════════-═══════════-═════════════-══════════════════-
║ Web2                 ║ Server    ║ 10.0.0.6    ║ Linux            ║
-══════════════════════-═══════════-═════════════-══════════════════-
║ ELK-SERVER           ║ Server    ║ 10.1.0.4    ║ Linux            ║
-══════════════════════-═══════════-═════════════-══════════════════-

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
10.0.0.4
70.122.4.34

Machines within the network can only be accessed by _____.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_

A summary of the access policies in place can be found in the table below.

╔══════════════════════╦═════════════════════╦══════════════════════╗
║ Name                 ║ Publicly Accessible ║ Allowed IP Adresses  ║
╠══════════════════════╬═════════════════════╬══════════════════════╣
║ Jump-Box-Provisioner ║ No                  ║ 10.0.0.4 70.122.4.34 ║
╠══════════════════════╬═════════════════════╬══════════════════════╣
║ Web1                 ║ Yes                 ║ Any                  ║
╠══════════════════════╬═════════════════════╬══════════════════════╣
║ Web2                 ║ Yes                 ║ Any                  ║
╠══════════════════════╬═════════════════════╬══════════════════════╣
║ ELK-Server           ║ No                  ║ 10.0.0.4             ║
╚══════════════════════╩═════════════════════╩══════════════════════╝

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because automating configurations makes cinfiguring multiple machines more efficient and removes human error.

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ...
- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

(Images/Docker-ps.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
10.0.0.5
10.0.0.6

We have installed the following Beats on these machines:
Filebeat 
Metricbeat

These Beats allow us to collect the following information from each machine:
Filebeat monitors logfiles and Metricbeat monitors metrics and statistics. Both Beats forward the information to Elasticsearch or Logstash.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
