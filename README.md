## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Path with the name of your diagram](Images/diagram_filename.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the ansible files may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Enter the playbook file._

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
- Beats in Use
- Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be accessable and responsive, in addition to restricting unwanted access to the network, as well as permitting access from certain addresses.
The jumpbox is used on the network to access nodes in many locations. This allows secure configuration protocols to be implemented, while also providing simple accessibility in development.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the docker containers and system logs.
- Filebeat watches and records the system logs for the Web 1 and 2 virtual machines. These logs are vital for seeing information about the virtual machines that host the public DVWA application.
- Metricbeat watches, records, and transmits information in regards to the performance of the web applications being hosted on the Web 1 and 2 virtual machines. Metricbeat also collects and transmits information from the system and the processes that are running.

The configuration details of each machine may be found below.

|   Name   |    Function   | IP Address | Operating System |
|:--------:|:-------------:|:----------:|:----------------:|
| Jump Box | Gateway       | 10.0.0.4   | Ubuntu 18.04.1   |
| Web VM 1 | Host the DVWA | 10.0.0.5   | Ubuntu 18.04.1   |
| Web VM 2 | Host the DVWA | 10.0.0.6   | Ubuntu 18.04.1   |
| ELK VM   | ELK Server    | 10.1.0.4   | Ubuntu 18.04.4   |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- Public IP of the user(s) allowed to SSH into the Jump Box VM.

Machines within the network can only be accessed through the Jump Box virtual machine.
- Web VM 1
	- Available from the Jump Box virtual machine.
- Web VM 2
	- Available from the Jump Box virtual machine.
- ELK Server VM
	- Available from Web 1 & 2 virtual machines.

Publically available domains:
- 40.88.37.103 (Damn Vulnerable Web Application)
	*** Currently only available to my public IP in order to reduce traffic ***

A summary of the access policies in place can be found in the table below.

|    Name    | Publicly Accessible |              Allowed IP Addresses            |
|:----------:|:-------------------:|:--------------------------------------------:|
| Jump Box   |          No         | SSH configured for admin user                |
| Web VM 1   |        Yes/No       | from *, port 80, to DVWA  (VM is private)    |
| Web VM 2   |        Yes/No       | from *, port 80, to DVWA  (VM is private)    |
| ELK Server |          No         | 10.0.0.5, 10.0.0.6                           |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ...
- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

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
