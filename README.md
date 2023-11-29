Aims/Description

To achieve a network that is secure, performs optimally, and is reliable, it is important to implement
Infrastructure as Code (IaC) principles. Additionally, redundancy should be considered to ensure that
the network is highly available. These measures can be achieved by setting up a mini-network that is
designed with a focus on security, performance, redundancy, and reliability. With these principles in
mind, the network can be made robust and efficient, ensuring that it functions optimally. The aim of
the mini-network structure is:
1. Design a mini-network for the online presence of a small company.
Assuming the network is primarily for the company website, we can start with a basic
setup. We'll need a web server to host the website and database server to handle the
data transactions. Finally, we should also consider security measures such as firewalls,
antivirus software, and SSL certificates to protect the website and its users from
potential threats.
2. Adapt the mini-network with the expansion of the company. This may involve adding
new infrastructure, upgrading existing systems, or reconfiguring the network to better
support the increased demands of the organization.
3. The application of good practices to the network is crucial for its proper functioning
and security. It ensures that the network operates efficiently and effectively while
minimizing the risk of cyber threats.

Method

1. The documentation related to CloudFormation, EC2, VPC, VPC Peering, Routing,
IGW, NAT Gateway, Security Groups, IAM, Three-Tier Architecture, RDS,
LoadBalancer, EIP was reviewed for relevance in building the mini network for company
2. I created an IAM user role and added it to a group. With this IAM user role, I am able
to access the AWS resources and build a mini-network.
3. CloudFormation templates were created with the necessary AWS resources and each
template is formated, seperated according to the tasks and paramaters from each
template are shared between them.
4. A Web Application is build using a three-tier web architecture. This architecture
consists of three layers, namely the Webpage layer, Php WebServer layer, and MySQL
database Server layer. As a result, users can access the company website
with ease.

Conclusion

When it comes to creating a website for a start-up company, architecting a solution with AWS
resources is a crucial aspect that needs to be carefully considered. The solution impacts the cost,
performance, security, and reliability of the website and the network. Therefore, it's important to
pay close attention to the architectural solution and ensure that it meets all the necessary
requirements. When using different AWS resources, regions, and zones, it's important to take into
account the cost of data transfers. If we use the Internet Gateway to access services within the same
region, there won't be any data transfer costs. However, if we use the NAT Gateway to access
services within the same region, data transfer costs will be incurred. Additionally, there is a data
charge that applies when data is transferred between two different regions.
I have considered VPC Peering as the first step for creating an architectural solution that involves a
web host server, MySQL EC2 instances in AZ1, and a replica for the availability of EC2 instances in
AZ2. I am planning to establish a VPC Peering connection between AZ1 and AZ2 to enhance
connectivity between the two availability zones. Based on the references, it seems that the
expenses associated with data transfers within workloads in the Availability Zone and VPC Peering
across different Availability Zones are quite high, according to my analysis. I have analyzed the AWS
three-tier architecture which is known for being modular, scalable, highly available, fault-tolerant,
secure, and cost-effective compared to VPC peering. I opted the Three-Tier Architecture since it's the
most fitting design for the start-up company solution's architecture.

The Three-tier architecture is a framework that comprises three distinct layers: the presentation
layer, logic layer, and data handling layer. In the case of start-up company, their design is built in the Three-
tier architecture format, where the presentation layer hosts the webpages, the logic layer (PHP
server is hosted) manages the request handling from users such as queries, and the data handling
layer contains the MySQL database that processes data-related queries from the logic layer. To
ensure our start-up company framework is fault-tolerant, secure, and highly available, we utilize AWS
services in addition to the three-tier architecture. With our current modular architecture, any faults
that occur are isolated to a specific module, allowing us to run the layers independently. This makes
it much easier to identify and fix issues as they arise.We have implemented a load balancer in our
architecture to ensure its scalability. This load balancer is responsible for distributing requests from
users to the web servers in the logical layer, thereby ensuring that the system is able to handle a
large number of requests efficiently. Our website is designed to be highly available and fault tolerant
as the EC2 instances of the logical and database layers are replicated into another Availability Zone
(AZ2).
To ensure that the Three-Tier architecture is secure, we have implemented several measures. The
presentation layer is made public, while the logical and data layers are kept private. Communication
is allowed from the presentation layer to the logical layer and from the logical layer to the data layer,
but there is no direct communication between the presentation and logical layers. The internet is
accessible only from the Presentation layer, which is in the public subnet with IGW. The logical and
data layers are in private subnets that have NAT gateways to allow for software upgrades and
installations.
We have also deployed a Bostion Host server EC2 instance in the presentation layer of the public
subnet. This ensures that the only access to the private subnets EC2 and other instances is through
the Bostion Host. To further strengthen the security, we have made the Bostion Host Server
accessible only through MyIP, which is my device's public IP.
I found that the AWS Three-tier Architectural Design with Boston Host and LoadBalancer, as well as
the security groups, IGW and NAT Gateway to be effective in completing the architecture with
security. It's always important to prioritize security when it comes to designing infrastructure in the
cloud. The role played by IAM is indeed crucial when it comes to security. Configuring the mini-
network architecture through IAM with Multi Factor Authentication can significantly increase the
level of security.

References

1. AWS CloudFormation, User Guide, “https://docs.aws.amazon.com/AWSCloudFormation/latest/
UserGuide/Welcome.html"
2. Amazon Elastic Compute Cloud, User Guide, “https://docs.aws.amazon.com/AWSEC2/latest/
UserGuide/concepts.html”
3. AWS Serverless Multi-Tier Architectures with Amazon API Gateway and AWS Lambda, AWS
Whitepaper, “https://docs.aws.amazon.com/whitepapers/latest/serverless-multi-tier-
architectures-api-gateway-lambda/three-tier-architecture-overview.html”
4. Amazon Virtual Private Cloud, User Guide, “https://docs.aws.amazon.com/vpc/latest/userguide/
what-is-amazon-vpc.html"
5. Amazon Virtual Private Cloud, VPC Peering, “https://docs.aws.amazon.com/vpc/latest/peering/
what-is-vpc-peering.html"
6. AWS Identity and Access Management, User Guide, “https://docs.aws.amazon.com/IAM/latest/
UserGuide/introduction.html"
7. Elastic Load Balancing, User Guide, “https://docs.aws.amazon.com/elasticloadbalancing/latest/
userguide/what-is-load-balancing.html"
8. Amazon Relational Database Service, User Guide, “https://docs.aws.amazon.com/AmazonRDS/
latest/UserGuide/Welcome.html"
9. Birender Pal, Sebastian Gorczynski, and Dennis Schmidt, Overview of Data Transfer Costs for
Common Architectures, “https://aws.amazon.com/blogs/architecture/overview-of-data-transfer-
costs-for-common-architectures/”
10. Install Php Web Server in the EC2 Instance, User Guide, “https://docs.aws.amazon.com/AWSEC2/
latest/UserGuide/ec2-lamp-amazon-linux-2.html"
