Amazon Virtual Private Cloud (VPC)



In this practice, an Amazon Private Cloud was created, configured and explored.





\---Creating a VPC



A VPC with one availability zone, 1 public subnet, private subnet was created.



For NAT Gateway, one AZ under the "Zonal" option and for VPC endpoints, none was chosen.





\---Exploring the VPC



The VPC Internet gateway, subnets and other features to edit or view could be found in the left in the navigation bar.



\### An Internet gateway connects your VPC to the Internet. If the Internet gateway was not present, then the VPC would have no connectivity to the Internet. An Internet gateway is a horizontally scaled, redundant and highly available VPC component. It therefore imposes no availability risks or bandwidth constraints on your network traffic.



\### A Subnet is a subset of a VPC. It belongs to a specific VPC, exists in a single AZ and has an IP address Range.



\### Routing rules are evaluated from the most restrictive (with the bigger number after the slash) through to the least restrictive (which is 0.0.0.0/0 since it refers to the entire Internet). Thus, traffic is first sent within the VPC if it falls within the range of the VPC, otherwise it is send to the Internet. The rules can further be edited based upon your particular network configuration.



\### The route table for the private subnet does not include a route to the Internet Gateway (IGW). This absence of a direct internet route is what defines this subnet as a private subnet. Instances in this private subnet cannot be directly accessed from the internet, providing an additional layer of security and isolation.



\### A Network Address Translation (NAT) gateway allows resources in a private subnet to connect to the Internet and other resources outside the VPC. This is an outbound-only connection, which means that the connection must be initiated from within the private subnet. Resources on the Internet cannot initiate an inbound connection. Therefore, it is a means of keeping resources private and improving security for VPC resources.



\### Security groups act as virtual firewall for your instances to control inbound and outbound traffic. When you launch an Amazon EC2 instance into a VPC, you can assign up to five security groups to the instance. Security groups act at the instance level and not the subnet level. Your VPC automatically comes with a default security group. If you do not specify a different security group when you launch an Amazon EC2 instance, it uses the default security group.



\### The default security group permits ALL traffic to access associated resources, but only if the Source is the default security group. This self-reference might appear strange, but this configuration simply means that any EC2 instance associated with the default security group can communicate with any other EC2 instance that is associated with the default security group. All other traffic is denied. This is a very safe default setting because it limits any access from other resources.



\### When adding resources to the VPC, you can create additional security groups to permit desired access to resources such as web servers, application servers and database servers.

