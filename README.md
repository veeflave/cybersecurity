Automated ELK Stack Deployment
The files in this repository were used to configure the network depicted below.
Note: The following image link needs to be updated. Replace diagram_filename.png with the name of your diagram image file.

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the YAML file may be used to install only certain pieces of it, such as Filebeat.

TODO: Enter the playbook file.

Answer:
	-install_elk.yml
	-my-playbook.yml
	-filebeat-playbook.yml
  
This document contains the following details:

Description of the Topology
Access Policies
ELK Configuration
Beats in Use
Machines Being Monitored
How to Use the Ansible Build

Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.
Load balancing ensures that the application will be highly efficient , in addition to restricting excessive accesses to the network.

TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?

Answer:
  -The security aspect of a load balancer is to manage the traffic of data coming into a server, and making sure that the server will not be overloaded. This can protect against DoDs attacks by control and shifting data to the desired server. 
  
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the Web Application and system server/host.

TODO: What does Filebeat watch for?

Answer:
  -Filebeat monitor and logs files on the specific location that the user wants, and the logs are forwarded to Elasticsearch.
  
TODO: What does Metricbeat record?

Answer:
	-Metricbeat records and monitors metrics collected from the system and services running on the server. 
The configuration details of each machine may be found below. Note: Use the Markdown Table Generator to add/remove values from the table.


Name      Function      IP Address      Operating System
Jump Box  Gateway       10.0.0.1        Linux
TODO      Web-1         10.0.0.5        Linux
TODO      Web-2         10.0.0.6        Linux
TODO      Elk           10.1.0.4        Linux

Access Policies

The machines on the internal network are not exposed to the public Internet.
Only the Jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:

TODO: Add whitelisted IP addresses

Answer:
	-My public IP address is whitelisted
  
Machines within the network can only be accessed by My computer.

TODO: Which machine did you allow to access your ELK VM? What was its IP address?

Answer:
	-The Jumpbox machine is allowed to access the Elk VM, and  it’s IP address is 52.146.44.252
  
A summary of the access policies in place can be found in the table below.

Name        Publicly Accessible       Allowed IP Addresses
Jump Box    Yes                       10.0.0.4

Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...

TODO: What is the main advantage of automating configuration with Ansible?

Answer:
	-Ansible saves time from tedious configurations and installing packages to many servers. 
  
The playbook implements the following tasks:

TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc.

Answer:
1. Set up an ELK virtual Network, Security group, and Virtual machine, as well as adding security rules to the Security group 
2. Add IP address of elk server into ansible configuration file
3. Write a YAML file to install docker, python3, and other modules 
4. Check to to see if Elk server is available on Kibana web browser
The following screenshot displays the result of running docker ps after successfully configuring the ELK instance.

Note: The following image link needs to be updated. Replace docker_ps_output.png with the name of your screenshot image file.

Target Machines & Beats

This ELK server is configured to monitor the following machines:

TODO: List the IP addresses of the machines you are monitoring

Answer:
	-10.0.0.5
	-10.0.0.6
  
We have installed the following Beats on these machines:

TODO: Specify which Beats you successfully installed

Answer:
	-Filebeat is the one that has been successfully installed on the elk machine. 
  
These Beats allow us to collect the following information from each machine:

TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., Winlogbeat collects Windows logs, which we use to track user logon events, etc.

Answer:
	-Filebeat collects system logs and services that are running on the server. Also, the application can probably register and monitor system events. 
  
Using the Playbook

In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:

SSH into the control node and follow the steps below:

  -Copy the YMAL file to the ansible directory.
  -Update the YMAL configs file to include IP addresses of the VMs
  -Run the playbook, and navigate to Virtual Machine to check that the installation worked as expected.
  
TODO: Answer the following questions to fill in the blanks:

Which file is the playbook? Where do you copy it?

Answer:
	-YAML file is used for the playbook. You copy it into the ansible directory.
Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?
-hosts
-ansible.conf
-YAML file

Which URL do you navigate to in order to check that the ELK server is running?
-http://13.64.224.197:5601/app/kibana#/home

As a Bonus, provide the specific commands the user will need to run to download the playbook, update the files, etc.

  -Sudo docker pull cyberxsecurity/ansible
	-nano my-playbook.yml
