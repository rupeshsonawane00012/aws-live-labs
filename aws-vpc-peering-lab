# aws-vpc-peering-lab

#AWS VPC Peering with Private EC2 Communication

This project demonstrates how to establish private communication between two AWS VPCs using VPC Peering, without using the internet, NAT Gateway, or public IPs.
The setup follows real-world AWS networking best practices, where services communicate over private IP addresses inside AWS’s internal network.

🏗️ Architecture

Two VPCs in the same AWS account and region
Non-overlapping CIDR blocks
One EC2 instance in each VPC
VPC Peering connection between the VPCs
Route tables updated to enable inter-VPC traffic
Security groups configured for ICMP and SSH
Connectivity verified using private IP addresses

🧠 Key Concepts Covered

VPC isolation
Non-overlapping CIDR planning
VPC Peering connection
Route table configuration
Security group rules
Private IP-based communication
secure SSH access without public exposure

VPC 1 (172.168.0.0/16)
 └── EC2 Instance (Private IP)
        |
        |  VPC Peering
        |
VPC 2 (192.168.0.0/16)
 └── EC2 Instance (Private IP)



⚙️ Step-by-Step Implementation
1️⃣ Create Two VPCs

VPC 1 CIDR: 172.168.0.0/16
VPC 2 CIDR: 192.168.0.0/16

CIDR blocks must not overlap.

2️⃣ Create Subnets
One subnet in each VPC
Instances launched without public IPs (private networking)

3️⃣ Launch EC2 Instances
Ubuntu Linux
One EC2 per VPC
No public IP assigned
Security groups allow:
ICMP (ping)
SSH (22) from the other VPC CIDR

4️⃣ Create VPC Peering Connection
Requester: VPC 1
Accepter: VPC 2
Peering status: Active

5️⃣ Update Route Tables
Add routes in both VPCs:
VPC 1 Route Table

Destination: 192.168.0.0/16
Target: VPC Peering Connection

VPC 2 Route Table

Destination: 172.168.0.0/16
Target: VPC Peering Connection

6️⃣ Verify Connectivity
From EC2 in VPC 1:
ping 192.168.1.97

From EC2 in VPC 2:
ping 172.168.0.202

✔ Successful ICMP replies confirm peering works.

7️⃣ SSH via Private IP
ssh ubuntu@<private-ip-of-other-ec2>


This confirms:
Private routing
Security group correctness
Real-world access pattern

🔐 Security Best Practices Followed
No public IPs on private instances
No internet gateway or NAT used for peering
Access restricted using security groups
Private communication only

# Cleanup (Cost Optimization)

After testing:
Terminated EC2 instances |
Deleted VPC peering connection|
Removed subnets and VPCs|
Released Elastic IPs|

 Ensured zero unexpected AWS costs

# What I Learned

How VPC Peering works internally
Importance of route tables in traffic flow
Difference between public and private access
Why NAT and IGW are not required for peering
How companies design secure AWS networks

# Skills Demonstrated
AWS Networking
VPC Design
Cloud Security
Linux & SSH
Troubleshooting AWS connectivity issues

# Author
Rupesh Gorakhnath Sonawane
B.Tech CSE | 
