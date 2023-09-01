Infrastructure Design:

Server 1: Primary Server (Web + App)
Server 2: Replica Server (Web + App)
Server 3: Database Primary (Master)
Load Balancer (HAproxy): Distributes traffic between Server 1 and Server 2.
Application Files (Your Code Base): Contains the website's application code.
Database (MySQL): Stores website data.
Server 1: Web + App Server (Primary)
Server 2: Web + App Server (Replica)
Explanation of Specifics:

Additional Elements:

Server 2: Added to provide redundancy and handle increased traffic loads.
Load Balancer (HAproxy): Added to distribute incoming traffic between the two application servers for load distribution and improved availability.
Server 3 (Database Primary): Added to form a Primary-Replica (Master-Slave) database cluster for data redundancy and scalability.
Load Balancer Distribution Algorithm:
The load balancer uses a Round Robin distribution algorithm. It cycles through the available servers in sequence, directing incoming requests to each server one after the other.

Active-Active vs. Active-Passive:
This setup is Active-Active. Both Server 1 and Server 2 actively handle user requests. Active-Active setups distribute the load across multiple servers, providing better performance and resource utilization.

Database Primary-Replica Cluster:
The Primary-Replica cluster consists of a Primary (Master) database (Server 3) and a Replica (Slave) database. The Primary node handles write operations and replicates data changes to the Replica node. The Replica node is used for read operations, reducing the load on the Primary node and providing data redundancy.

Difference Between Primary and Replica in Regards to the Application:
The Primary node handles write operations, making it responsible for updating and maintaining the most up-to-date data. The Replica node is read-only, serving as a backup for data retrieval. The application can direct read queries to the Replica node to offload read traffic from the Primary node.

Issues with the Infrastructure:

Single Points of Failure (SPOF):

If the Primary server (Server 1) goes down, there's a potential for service interruption.
The Load Balancer itself can become a SPOF. If it fails, traffic distribution stops.
Security Issues:

No firewall mentioned, leaving the servers exposed to potential attacks.
No HTTPS, which means that data transmission between users and servers is not encrypted.
No Monitoring:

Without monitoring tools, it's challenging to detect and address performance issues or potential security breaches.
To address these issues, implementing redundancy, security measures (like firewalls and HTTPS), and setting up monitoring tools would be essential. This would enhance the infrastructure's availability, security, and reliability.
