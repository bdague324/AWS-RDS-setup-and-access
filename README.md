# AWS RDS setup and access
 Tutorial

 ## Database not publicly accessible
 ###Architecture
 **VPC**
 * IGW
 * Subnet1 Private in AZ1
 * Subnet2 Private in AZ2 (different from AZ1)
 * Subnet3 Public
 ** Route table: RT-table -> add 0.0.0.0/0 to IGW

 **RDS instance**
 See create database instance below

 **EC2 Instance**
 * belongs to Subnet3
 * Public IP

 SG1:

 allow Inbound SSH from local
 allow Outbound All traffic
 Create Database (not publicly accessible)
 Create database (example MariaDB)

# Create Database (not publicly accessible)
* Create database (example mysql)

## Setting
* Choose the service RDS from AWS,
* Choose Standard create,
* Choose MySQL as engine type,
* Give a name to your DB instance: Database_1
* Give a Master username: admin
* Give your password :*********
* Confirm your password: *********

![Légende](create_RDS.PNG)

![Légende](Settings.PNG)

## Creation method and engine option

![Légende](Engine.PNG)

## Template

* Choose the free tier template available for 12 months.

![Légende](Template.PNG)

## Connectivity

* Don't choose the VPC security group by default.

## Security Group description

By Default Security group is created only for your current IP (Source). To be able to connect, it needs to be changed:



![Légende](Connect_conf.PNG)

## Additional configurations

* Do not enable automatic backups

![Légende](Data_base_options.PNG)

## Screen during Database Creation

![Légende](creating.PNG)

## Connection information

![Légende](Endpoint.PNG)

# Connect to the data base called Database_1

![Légende](Linux_connect.PNG)

## Connect to the database using Linux:

![Légende](Linux_create.PNG)

## Connect to the database using MYSQL:

![Légende](Connection_MYSQL.PNG)
![Légende](Check_connection.PNG)
![Légende](Table_display_MYSQL.PNG)

## Connect to the database via using Python)

The installation of the package called pymysql is needed.

Herebelow the script Python to connect to the database.

![Légende](Script_connection.PNG)

Herebelow the result of the request on Python. A list of the different database.

![Légende](List_database_Python.PNG)

The table called student is found by the following commands:

![Légende](Table_retrieve_python.PNG)


# Create Database (publicly accessible)

* The DNS resolution and DSN hosnames should be set at enable.
* When creating the RDS instance, this last one is set as Publicly accessible. 

### Useful commands:

* SHOW TABLES;
* DESCRIBE table;
* DROP TABLE table;
* Create table (SQL):

**Architecture**

# VPC
* Subnet1 in AZ1
* Subnet2 in AZ2 (different from AZ1)

# RDS instance
* Enable DNS resolution and DNS hostnames for your VPC
