Infrastructure Design:

Server 1: Web Server + Application Server
Server 2: Web Server + Application Server
Server 3: MySQL Database Server (Primary)
Load Balancer (SSL Termination): Terminates SSL and directs traffic to servers.
Firewalls: Placed around each server to enhance security.
SSL Certificate: Used to serve www.foobar.com over HTTPS.
Monitoring Clients: Collect data for monitoring and analysis.
Explanation of Specifics:

Additional Elements:

Firewalls: Added for security, protecting each server from unauthorized access.
SSL Certificate: Added to secure the connection between users and the website, encrypting data in transit.
Monitoring Clients: Added to collect data on server performance, availability, and other metrics.
Purpose of Firewalls:
Firewalls are added to control incoming and outgoing network traffic, preventing unauthorized access and enhancing security.

HTTPS for Encrypted Traffic:
HTTPS is used to encrypt the communication between users' browsers and the server. This ensures data privacy and prevents eavesdropping.

Monitoring Purpose:
Monitoring is used to track the performance, availability, and health of the infrastructure. It helps identify issues and optimize resources.

Monitoring Data Collection:
Monitoring clients collect data on various metrics, like server CPU usage, response times, traffic, etc., and send this data to monitoring services like Sumo Logic.

Monitoring Web Server QPS:
To monitor web server QPS (Queries Per Second), you can set up the monitoring tool to track the incoming request rate on the web servers.

Issues with the Infrastructure:

SSL Termination at Load Balancer Level:
Terminating SSL at the load balancer can expose decrypted traffic within the internal network, potentially compromising security.

Single MySQL Server Accepting Writes:
Having only one MySQL server that can accept writes introduces a single point of failure. If the MySQL server fails, write operations are impacted.

Uniform Server Components on All Servers:
Having identical components (database, web server, application server) on all servers might lead to resource inefficiency. Not all servers may require the same resources.

To address these issues, consider implementing SSL offloading securely, using database replication for redundancy, and optimizing resource allocation based on server roles and requirements.
