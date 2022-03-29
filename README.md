# Elk-Stack-Project
 This ELK-project simulates a monitoring system, by using azure to create VMs that allow for real time analytics and log correlation.
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

/c/Users/gussm/Elk-Stack-Project/Diagrams/'Elk-satck diagram.pdf'

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively,>

  - ~/Elk-Stack-Project/Ansible/filebeat-config.yml

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting acess to the network.
- Load balancers froma a denial of service attack by provising diffrent servers to use while one is down. Using a jumpbox allows for a direct conection to the vms and pro>

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the log files and system performance.
- Filebeat's role is that of a logging agent which fowards data to Logstash for processing.
- Metricbeat takes the metrics and statistics that it collects and ships them to the output that you specify, such as Elasticsearch or Logstash. Metricbeat helps you moni>

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump box | gateway  | 10.0.0.4   | Linux            |
| Web-1    | VM       | 10.0.0.6   | Linux            |
| web2     | VM       | 10.0.0.5   | Linux            |
| Dogvm    | Elk      | 10.1.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet.

Only the jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses: 99.82.193.67

Machines within the network can only be accessed by 10.0.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Public Accessible | Allowed IP Address |
|----------|-------------------|--------------------|
| Jump box | no                | 99.82.193.67       |
| VMS      | no                | 10.0.0.4           |
| ELK      | no                | 10.0.0.4           |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- Ansible is able to run scipts identically across platforms allowinf for fewer mistakes

The playbook implements the following tasks:
- Changing the memory of the ELK VM
- Installing Docker
- installing python-pip
- Downloading and launching docker ELK stack

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

 ~/Downloads/README/images/docker-ps.PNG

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
-10.0.0.6
-10.0.0.5

We have installed the following Beats on these machines:
- filebeat-7.4.0-amd64.deb

These Beats allow us to collect the following information from each machine:
- Filebeat is set up to monitor and collect log data from the web vms sends the log files to kibana.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:

SSH into the control node and follow the steps below:
- Copy the Filebeat-configuration.yml file to ELK vm.
- Update the hots file to include 10.0.0.6 , 10.0.0.5
- Run the playbook, and navigate to Kibana to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- filebeat-playbook.yml
- we can copy it by doing copy /etc/ansible/roles/filebeat-playbook.yml  to /etc/filebeat/filebeat.yml
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Fi>
-to update ansible we run update filebeat-playbook.yml. To make sure that it only run on the elk VM we update the host file by inputing that specifc Vm's IP address
- _Which URL do you navigate to in order to check that the ELK server is running?
-  http://20.230.119.17:5601/app/kibana

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
git pull
git add
git commit -m
git push origin --set-upstream <-branch->
