# Database Service

## Type of Database

- Relational Database Service (RDS): MySQL (MarioDB, Aurora, PostgreSQL, MSSQL and Oracle)
- DynamoDB: NoSQL, serverless service, high speed, low latency
- Redshift: Fast fully managed petabyte scale data warehouse based on PostgreSQL.
- Amazon Neptune: Fast, reliable fully managed graph database service. Purposed built high performance graph database engin optimized for storing billions of relationships and clearing the graph with millisecond latency.

## Database Related Services

- AWS Database Migration Service (DMS): Migrate a database to AWS easily and securely. Also migrate data from one database engine type to another different database engine type totally.
- ElastiCache: Cache in the cloud, allow you to retrieve information from fast fully managed in-memory caches instead of relying for slow disk based databases.

## Database Example

### Onsite to AWS

1. Launch a RDS Aurora DB instance in AWS VPC.
2. Use database migration service (workflow/job) to migrate data from onsite database to target Aurora.

### Optimisation

*Continue From Above*

1. RDS instance got overwhelming request.
2. Set up an ElastiCache node in front of that RDS instance, to **reduce latency**, any request not in elastication **will be forwarded** to RDS instance.
3. Less frequent accessed data can be accessed directly from RDS instance.

## RDS Lab

1. Create free tier RDS based on MySQL CE engine.
2. Connect to RDS through endpoint, use software: MySQL Workbench, DataGrip etc. Here use MySQL Workbench, can also use MySQL Shell.

*N.B. MySQL default port at 3306*

### If Using MySQL Workbench

1. MySQL Workbench -> MySQL Connections -> Plus Sign -> Hostname = endpoint -> Username = username created at RDS -> Test Connection -> Enter Password
2. If normal connection, from above, double click on instance on MySQL Workbench
3. When connected, on schema, if click i sign, will display information

### If Using MySQL Shell

1. Download MySQL Shell
2. Enter Shell -> \connect username@endpoint
3. Enter password
4. Change to SQL mode: \sql, set schema: \use schema

Some SQL command:

* SHOW DATABASES/TABLES/SCHEMAS;