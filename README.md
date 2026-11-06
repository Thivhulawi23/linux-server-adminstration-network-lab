# Linux Server Administration and Network Deployment Lab

## Project Overview

This project is based on an Operating Systems 2 practical using openSUSE Leap 16.0 in VirtualBox. The scenario involves Vaal Smart Energy, a small energy-monitoring company that needs an internal Energy Meter Dashboard to display smart meter readings stored in a database. The practical focuses on setting up a Linux server and client environment, configuring network connectivity, managing a MariaDB database, deploying a web application using Apache and PHP, and applying basic system security measures.

## Project Objectives

The main objectives of this practical are to:

1. Set up an openSUSE Leap 16.0 Linux lab environment using VirtualBox.
2. Configure server and client virtual machines for communication over a private Host-only network while retaining internet access through NAT.
3. Assign static IP addresses and verify network connectivity between the server, client and internet.
4. Install and configure MariaDB to store smart meter readings in a structured database.
5. Create database users and permissions according to the principle of least privilege.
6. Deploy an Energy Meter Dashboard using Apache and PHP.
7. Configure the system firewall to allow web traffic while keeping database access restricted to the local server.
8. Test, troubleshoot, and verify system services, database operations, web application access, and network connectivity.
9. Practise Linux system administration, service management, networking, database configuration, and basic security.

## Technologies & Tools

The following tools and technologies were used to prepare the lab environment:

- Oracle VirtualBox: Used to create and manage the virtual machines.
- openSUSE Leap 16.0: Linux operating system installed in the virtual machines.
- Virtual Machine Cloning: The original virtual machine was cloned to create the separate server and client machines. The cloned machines were assigned new MAC addresses to distinguish them on the network.
- RAM Allocation: Server VM: 4096 MB & Client VM: 2048 MB.
- Networking: Virtual networking was configured to support communication between the server and client machines.
- Linux Command Line: Used for system configuration, administration, and testing.
- MariaDB: Relational database management system used to store smart meter readings.
- Apache HTTP Server: Used to host the Energy Meter Dashboard.
- PHP: Used to execute the server-side application and retrieve database information.

## Part A: Lab Environment Setup

### 1. Virtual Machine Preparation

The lab environment was prepared using Oracle VirtualBox running on an Ubuntu Desktop host, with openSUSE Leap 16.0 installed as the guest operating system. The original virtual machine was cloned to create two separate virtual machines, which were designated as the server and client. New MAC addresses were generated for the cloned machines to distinguish their network adapters. The VMs were assigned the following memory allocations: Server VM retained the 4096 MB and the Client VM was reduced to 2048 MB.

### 2. Network Configuration

Both virtual machines were configured with two network adapters:

- NAT (Network Address Translation): Configured to provide internet connectivity to the virtual machines.
- Host-only Adapter: Configured to establish a private network for communication between the server and client.

### 3. Network Configuration Details

|Configuration        |Server VM              |Client VM         |
------------------------------------------------------------------
| Hostname            |   energy-server      |  energy-client    |
| Host-only IP        |  192.168.56.20/24    | 192.168.56.21/24  |

## Part B: Database and Web Server Configuration

### 1. MariaDB Database Setup

MariaDB was installed and configured on the server VM to store smart meter readings for the Vaal Smart Energy.

The database configuration involved:

- Starting and enabling the MariaDB service.
- Securing the database installation.
- Creating the energydb database.
- Creating the meter_readings table to store smart meter readings.
- Creating a dedicated database user named meteruser.
- Configuring database permissions according to the principle of least privilege.
- Importing smart meter readings from the meter_readings CSV file.
- Restricting database access to local connections.

### 2. Apache and PHP Web Server Setup

Apache and PHP were configured to host the Energy Meter Dashboard on the server VM.

The web application setup involved:

- Configuring the Apache web server.
- Setting up the PHP application using the provided meters.php file.
- Connecting the web application to the MariaDB database.
- Configuring the application to use a dedicated database account rather than the database root account.
- Ensuring the web server could access the required application files

### 3. Security and Service Configuration

Basic Linux security and service management practices were applied during the setup.

These included:

- Configuring services to start automatically at boot.
- Configuring the firewall to permit HTTP traffic.
- Keeping the MariaDB database port inaccessible to external network connections.
- Applying appropriate security contexts to web application files.
- Using restricted database permissions to reduce unnecessary access.

### 4. Testing and Verification

The completed environment was tested to verify that the required services and application worked as expected.

The verification tasks included:

- Checking the status of the MariaDB and Apache services.
- Verifying database connectivity.
- Checking that the dashboard displayed the smart meter readings.
- Testing access to the dashboard from the client machine.
- Verifying network connectivity between the server and client.
- Confirming that the firewall and database access restrictions were configured correctly.

## Lessons Learned
This practical strengthened my hands-on experience in Linux administration and server configuration.

Key lessons includes:
- Creating and managing virtual machines using VirtualBox.
- Configuring server and client environments.
- Understanding NAT and Host-only networking.
- Assigning static IP addresses and testing network connectivity.
- Installing and managing Linux services.
- Creating databases, tables, database users, and permissions using MariaDB.
- Applying basic Linux security practices and principle of least privilege.
- Testing configurations and troublesshoting system issues.

## Results and Evidence

The screenshots below document the lab setup, network configuration, database configuration, web server deployment and the Energy Meter Dashboard displayed in Firefox.

### Part A: Lab Environment Setup
![Server Network Configuration](images/energy-server%20Network_Configuration.png)
![Client Configuration](images/energy-client%20Network_Configuration.png)

### Part B: Database Configuration
![Database Package installed on Server](images/energy-server%20mariadb_package_installed.png)
![database secured](images/energy-server%20mariadb_secured.png)
![Database Verification](images/energy-server%20database%20verification.png)
![PHP Script changes](images/energy-server%20php%20script%20changes.png)
![Installing and Deploying Apache](images/energy-server%20Deploy%20the%20php%20page.png)
![Database settings check](images/energy-server%20database%20settings%20check.png)
![Logging as new user](images/energy-server%20successfully%20logged%20in%20as%20new%20user.png)
![Load from CSV file](images/energy-server%20Load%20sensor%20data%20from%20a%20csv%20file.png)
![Check for CSV](images/energy-server%20check%20for%20csv.png)
![Install and start PHP](images/energy-server%20install%20and%20start%20php.png)
![Deploy PHP page](images/energy-server%20Deploy%20the%20php%20page.png)
![Openning the Firewall](images/energy%20server%20openning%20firewall.png)
![Test from client](images/energy-client%20Testing%20from%20client.png)
![Testing from client Firefox searchbar](images/energy-client%20%20successfully%20got%20the%20page%20from%20firefox.png)

## Troubleshooting

- One challenge I have encountered during the practical was creating database tables and users. Small syntax errors caused commands to fail, requiring me to review the commands, identify mistakes and correct them. This helped me understand the importance of accurate syntax, reading error messages and checking commands during database configuration.
![Troubleshooting](images/Syntax%20errors%20creating%20the%20table%20with%20specified%20types.png)

## Conclusion

This practical provided me with an opportunity to apply theoretical Operating Systems 2 concepts in a hands-on Linux environment. By configuring virtual machines, networking, database services, and a web application, I strengthened practical experience in Linux system administration, service management, networking and basic system security.