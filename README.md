# ELK-Project-
For this assignment, we were requested  to arrange an ELK stack worker to set up a cloud observing framework. This undertaking will bring about substantial expectations that show your insight into cloud, network security, logging and checking.
## Automated ELK Stack Deployment
 
The files in this repository were used to configure the network depicted below.
 
![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)
These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the /etc/ansible/elk-playbook.yml file may be used to install only certain pieces of it, such as Filebeat.
 _TODO: Enter the playbook file. /etc/ansible/elk-playbook.yml
This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
 - Beats in Use
 - Machines Being Monitored
- How to Use the Ansible Build
 
 
### Description of the Topology
 
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.
 
Load balancing ensures that the application will be highly responsive and increases availability, in addition to restricting server overloads to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box? Load Balancers inhibit DDos attacks by shifting attack traffic. 
 
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system traffic.
- _TODO: What does Filebeat watch for? Filebeats screens any recorded log documents and advances them to Elasticsearch or Logstash.
 
- _TODO: What does Metricbeat record? Metricbeats collects metrics and statistics from an operating system and from services running on the server. 
 
 
 
The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator] to add/remove values from the table_.
### Access Policies
 
The machines on the internal network are not exposed to the public Internet.
 
Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses
   - 24.47.178.11
 
Machines within the network can only be accessed by ip address.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address? My IP 24.47.178.11
 
A summary of the access policies in place can be found in the table below.
### Elk Configuration
 
Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because services running can be limited, system installation and update can be streamlined, and processes become more replicable.
 
- _TODO: What is the main advantage of automating configuration with Ansible? 
 The main advantage of automating configuration with Ansible is that it simplifies the workload for IT employees and allows them to monitor computer systems more easily. 
 
 
The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc.
Introduce: docker.io 
Introduce: python-pip 
Introduce: docker 
Order: sysctl - w vm.max_map_count=262144 
Dispatch docker holder: elk
 
The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.
### Target Machines & Beats
This ELK server is configured to monitor the following machines:Web-1(10.0.0.12) and Web-2 (10.0.0.10)
 
We have installed the following Beats on these machines:
-TODO: Specify which Beats you successfully installed: Filebeat and Metricbeat 
 
These Beats allow us to collect the following information from each machine: Filebeat and Metricbeat 
 
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc.
Filebeat gathers logs and documents. Metricbeat gathers measurements from PC frameworks.
 
 
### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:
 
SSH into the control node and follow the steps below:
- Copy the hosts file to here 
- Update the hosts file to include…ELK and the web servers 
- Run the playbook, and navigate to Kibana to check that the installation worked as expected.
 
_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it /etc/ansible/file/filebeat-configuration.yml/ http://%5Byour.ELK-VM.External.IP%5D:5601
 
- _Which file do you update to make Ansible run the playbook on a specific machine? 
Change the /etc/ansible/host file to add web server/elk server ip addresses
 
How do I specify which machine to install the ELK server on versus which to install Filebeat on? 
Filebeat is a transporter, which gathers, totals and advances logs to your ideal yield (logstash, elasticsearch and so on) It fills in as a specialist, so you need to introduce it in each hub from which you need to gather logs from. For example, on the off chance that you need to gather logs from your neighborhood machine, at that point introduce filebeat there, in the event that you need to gather from the logstash worker itself, at that point introduce filebeat there. In the event that you need to gather logs from both, at that point filebeat should be introduced in the two machines.
 
- _Which URL do you navigate to in order to check that the ELK server is running?
    http://%5Byour.ELK-VM.External.IP%5D:5601
 
_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc. ansible-playbook filebeat-playbook.yml
 
