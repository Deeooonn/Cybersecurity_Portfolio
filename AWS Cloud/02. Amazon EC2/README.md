AMAZON EC2 instance



This lab includes all the main functions of the Amazon EC2. I create a web server running on a Linux machine in the cloud and demonstrate how to monitor, use and terminate the web server.



\---Launch and Monitor instance



Checked the status tab for hardware and software issues



Monitored the instance using CloudWatch metrics in the monitoring tab



Scrolled through system log and confirmed that the httpd user package was installed from the user data added when creating the instance.



Attained instance screenshot using the Monitor and Troubleshoot section



\---Updated Security Group

Trying to access content from the web server was impossible due to the security group as a firewall restricting the traffic.



In the, security group section, the Web Server security group was edited to include a new inbound rule





\---Resize Instance: Instance Type and EBS volume



\#### When you stop an instance, it is shut down. There is no charge for a stopped EC2 instance, but the storage charge for attached Amazon EBS volumes remains.



Changed the instance to an instance twice as large as the current t3.micro --> t3.small



Modified the volume size to 10 GB from 8 GB



Restart Instance



\---Terminate Instance with existing termination protection



Instance failed to delete due to termination protection

