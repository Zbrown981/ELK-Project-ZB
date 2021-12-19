# ELK-Project-ZB
ELK Project Documentation 
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

(ELK-Project-ZB/Diagrams/ELK Network Diagram.PNG)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the Ansible file may be used to install only certain pieces of it, such as Filebeat.

 (ELK-Project-ZB/Ansible)

This document contains the following details:
- Description of the Topology
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

| Name      | Function | IP Address | Operating System |
|-----------|----------|------------|------------------|
| Jump Box  | Gateway  | 10.0.0.4   | Linux            |
| Web1      | Server   | 10.0.0.5   | Linux            |
| Web2      | Server   | 10.0.0.6   | Linux            |
| ELK-Server| Server   | 10.1.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
10.0.0.4
70.122.4.34

Machines within the network can only be accessed by 10.0.0.4.

A summary of the access policies in place can be found in the table below.

| Name       | Publicly Accessible | Allowed IP Addresses |
|------------|---------------------|----------------------|
| Jump Box   | Yes/No              | 10.0.0.4 70.122.4.34 |
| Web1       | Yes                 | Any                  |
| Web2       | Yes                 | Any                  |
| ELK-Server | No                  | 10.0.0.4 70.122.4.34 |


### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because automating configurations makes configuring multiple machines more efficient and removes human error.

The playbook implements the following tasks:
- Install docker.io
- Installs pip3
- Install docke python module
- Enables system to use more memory
- Downloads and launches docker elk container 

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

(Images/ELK-Docker-ps.png)

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
- Copy the elkplaybook file to the ansible directory.
- Update the hosts file to include your new elk VM.
- Run the playbook, and navigate to kibana on your browser (http://<elk-server-ip>:5601/app/kibana) to check that the installation worked as expected. 

### Commands to download and run the playbook
Navigate to you Ansible directory
  run "nano hosts", add an [elk] group and add the IP address to your new VM.
Create a playbook to configure your elk server.
  run "touch /etc/ansible/elkplaybook.yml" and write tasks that will:
                                      - Install docker.io
                                      - Install pip3
                                      - Install docker python module
                                      - Enable system to use more memory
                                      - Download and launch docker elk container
                                      - Enable docker on boot
Run the playbook.
  run "ansible-playbook elkplaybook.yml"
After the playbook completes ssh into your elk VM and run "docker ps". In the ouptut, you should see a single row whose second column is "sebp/elk"
If everything is correct, navigate to http://<elk-server-ip>:5601/app/kibana in your browser and the elk site should be up.
