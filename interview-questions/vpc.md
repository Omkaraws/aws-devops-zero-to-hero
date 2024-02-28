Public Subnet: if a subnet’s traffic is routed to an internet gateway, the subnet is known as public subnet. If you want your instance in a public subnet to communicate with the internet over IPV4,
it must have a public IPV4 address or an Elastic IP address.
Private Subnet: if a subnet doesn’t have a route to the internet gateway, the subnet is known as private subnet. When you create a VPC you must specify an IPV4 CIDR block for the VPC. The allowed blocks size is between /16 to /28 networks. The first four and last IP address of subnet cannot be assigned.\

The instances in the public subnet can send outbound traffic directly to the internet, but instances in private subnet can’t.
For e.g: 10.0.0.0- network address
10.0.0.1- reserved by AWS for the VPC router
10.0.0.2- reserved by AWS the IP address of DNS server
10.0.0.3- reserved for future use
10.0.0.255- broadcast address
Note: AWS do not support broadcast in a VPC but reserve this address.



### 1. What is Amazon Virtual Private Cloud (VPC)?
Amazon VPC is a logically isolated section of the AWS Cloud where you can launch resources in a virtual network that you define. It allows you to control your network environment, including IP addresses, subnets, and security settings.

### 2. What are the key components of Amazon VPC?
Key components of Amazon VPC include subnets, route tables, network access control lists (ACLs), security groups, and Virtual Private Gateways (VPGs).

### 3. How does Amazon VPC work?
Amazon VPC enables you to create a private and secure network within AWS. You define IP ranges for your VPC, create subnets, and configure network security.

### 4. What are VPC subnets?
VPC subnets are segments of the VPC's IP address range. They allow you to isolate resources and control access by creating public and private subnets.

PUBLIC SUBNET: if subnet's traffic is routed to an internet gateway, the s.n. is knownn as public subnet
PRIVATE SUBNET: if subnet doesn't have a route to the internet gateway 

### 5. How can you connect your on-premises network to Amazon VPC?
You can establish a Virtual Private Network (VPN) connection or use AWS Direct Connect to connect your on-premises network to Amazon VPC.

### 6. What is a VPC peering connection?
VPC peering allows you to connect two VPCs together, enabling resources in different VPCs to communicate as if they were on the same network.

### 7. What is a route table in Amazon VPC?
A route table defines the rules for routing traffic within a VPC. It determines how traffic is directed between subnets and to external destinations.

### 8. How do security groups work in Amazon VPC?
Security groups act as virtual firewalls for your instances, controlling inbound and outbound traffic. They can be associated with instances and control their network access.

### 9. What are network access control lists (ACLs) in Amazon VPC?
Network ACLs are stateless filters that control inbound and outbound traffic at the subnet level. They provide an additional layer of security to control traffic flow.

### 10. How can you ensure private communication between instances in Amazon VPC?
You can create private subnets and configure security groups to allow communication only between instances within the same subnet, enhancing network security.

### 11. What is the default VPC in Amazon Web Services?
The default VPC is a pre-configured VPC that is created for your AWS account in each region. It simplifies instance launch but doesn't provide the same level of isolation as custom VPCs.

### 12. Can you peer VPCs in different regions?
No, VPC peering is limited to VPCs within the same region. To connect VPCs across regions, you would need to use VPN or AWS Direct Connect.

### 13. How can you control public and private IP addresses in Amazon VPC?
Amazon VPC allows you to allocate private IP addresses to instances automatically. Public IP addresses can be associated with instances launched in public subnets.

### 14. What is a VPN connection in Amazon VPC?
A VPN connection allows you to securely connect your on-premises network to your Amazon VPC using encrypted tunnels over the public internet.

### 15. What is an Internet Gateway (IGW) in Amazon VPC?
An Internet Gateway enables instances in your VPC to access the internet and allows internet traffic to reach instances in your VPC.

### 16. How can you ensure high availability in Amazon VPC?
You can design your VPC with subnets across multiple Availability Zones (AZs) to ensure that your resources remain available in the event of an AZ outage.

### 17. How does Amazon VPC provide isolation?
Amazon VPC provides isolation by allowing you to define and manage your own virtual network environment, including subnets, route tables, and network ACLs.

### 18. Can you modify a VPC after creation?
While you can modify certain attributes of a VPC, such as its IP address range and subnets, some attributes are immutable, like the VPC's CIDR block.

### 19. What is a default route in Amazon VPC?
A default route in a route table directs traffic to the Internet Gateway (IGW), allowing instances in public subnets to communicate with the internet.

### 20. What is the purpose of the Amazon VPC Endpoint?
An Amazon VPC Endpoint enables you to privately connect your VPC to supported AWS services and VPC endpoint services without needing an internet gateway or VPN connection.

### NAT GATEWAY: u can use it for enable instance in a private S.N. to connect to a internet.
NAT Gateway:
You can use a network address translation gateway to enable instances in a private subnet to connect to the internet or other AWS services but prevent the internet from initiating a connection with those instances.

You are charged for creating and using a NAT gateway in your account. NAT gateway hourly usage and data processing rates apply. Amazon EC2 charges for data transfer also apply.

To create a NAT gateway, you must specify the public subnet in which the NAT gateway should reside.

You must also specify an elastic IP address to associate with NAT gateway when you create it.

No need to assign public IP address to your private instance.
After you have created a NAT gateway you must update the route table associated with one or more of your private subnets to point internet bound traffic to the NAT gateway. This enables instances in your private subnet to communicate with the internet.

Deleting a NAT gateway, disassociates its elastic IP address, but does not release the address from your account.

### Implied Router and Routing Table:
 It is the central routing function.
 It connects the different AZ together and connects the VPC to the internet gateway.
 You can have up to 200 route tables per VPC.
 You can have up to 50 routes entries per route table.
 Each subnet must be associated with only one route table at any given time only.
 If you don’t specify a subnet to route table association, the subnet will be associated with the default VPC route table.
 You can also edit the main route table if you need but you cannot delete the main route table.
 However you can make a custom route table manually become the main route table then you can delete the former main as it is no longer a main route table.
 You can associate multiple subnets with the same route table.

C. Internet Gateway:
 An internet gateway is a virtual router that connects a VPC to the internet.
 Default VPC is already attached with an internet gateway.
 If you create a new VPC then you must attach the internet gateway in order to access the internet.
 Ensure that your subnet’s route table points to the internet gateway.
 It performs NAT between your private and public IPV4 address.
 It supports both IPV4 and IPV6.

Security Group:
 It is a virtual firewall works at ENI level.
 Up to 5 security groups per EC2 instance interface can be applied.
 Can only have permit rules, cannot have deny rules.
 Stateful, return traffic of allowed inbound traffic is allowed even if there are no rules to allow it.


E. NACL:
 It is a function performed on the implied router.
 NACL is an optional layer of security for your VPC that acts as a firewall for controlling traffic in and out of one or more subnets.
 Your VPC automatically comes with a modifiable default NACL. By default, it allows all inbound and outbound IPV4 traffic and if applicable IPV6 traffic.
 You can create a custom NACL and associate it with a subnet. By default each NACL denies all inbound and outbound traffic until you add rules.
 Each subnet in your VPC must be associated with a NACL. If you don’t explicitly associate a subnet with a NACL, the Subnet is automatically associated with the default NACL.
 You can associate a NACL with multiple subnets; however a subnet can be associated with only one NACL at a time. When you associate a NACL with a subnet the previous association is removed.
 A NACL contains a numbered list of rules that we evaluate in order starting with the lowest numbered rule.
 The highest number that you can use for a rule is 32766. Recommended that you start by creating rules with rule numbers that a multiple of 100, so that you can insert new rules where you need later.
 It functions at the subnet level.
 NACL are stateless, outbound traffic for an allowed inbound traffic must be explicitly allowed too.
 You can have permit and deny rules in a NACL.


VPC Peering:
 A VPC peering connection is a network connection between two VPC that enables you to route traffic between them using private IPV4 addresses or IPV6 addresses.
 Instances in either VPC can communicate with each other as if they are within the same network.
 You can create a VPC peering connection between your own VPC or with a VPC in another AWS account. The VPC can be in different region
