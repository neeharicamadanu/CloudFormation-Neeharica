Aims/Description
To achieve a network that is secure, performs optimally, and is reliable, it is important to implement
Infrastructure as Code (IaC) principles. Additionally, redundancy should be considered to ensure that
the network is highly available. These measures can be achieved by setting up a mini-network that is
designed with a focus on security, performance, redundancy, and reliability. With these principles in
mind, the network can be made robust and efficient, ensuring that it functions optimally. The aim of
the mini-network structure is:
1. Design a mini-network for the online presence of FridayHITT small company.
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
