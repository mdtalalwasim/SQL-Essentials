# SQL-Essentials
SQL-Essentials

#### Duplicate Check in Table:
```bash
SELECT imei, COUNT(imei)
FROM tokens
GROUP BY imei
HAVING COUNT(imei) > 1

```


#### Total Count from Table:
```bash
SELECT COUNT(*) AS TotalCount FROM table_name;
```

#### Fetch Data in Descending Order 0 to 100 ORDER BY ID:
```bash
SELECT id FROM devices ORDER BY id DESC LIMIT 0, 100;
```


#### Database Backup:
```bash
mysqldump -u user_name -p db_name > save_file_name.sql;
```


#### All Base Table Count:
```bash
USE Database_Name
SELECT Count(*)
FROM INFORMATION_SCHEMA.TABLES
WHERE TABLE_TYPE = 'BASE TABLE';
```


#### Database Specific Table Count:
```bash
USE Database_Name
SELECT COUNT(*)
FROM information_schema.tables
WHERE table_schema = 'Database_Name';

```

#### Database Specific Table Count [Alternative Way]:
```bash
USE Database_Name;
SHOW TABLES;
SELECT FOUND_ROWS();
```


#### Database Specific Table Count:
```bash
USE Database_Name
SELECT COUNT(*)
FROM information_schema.tables
WHERE table_schema = 'Database_Name';
```


#### Import Local Database to Liver Server Database (on linux server):
##### 1. Access Your Live Server via SSH
First, you'll need to connect to your live server using SSH. You can do this from your local terminal (Linux/Mac) or using a tool like PuTTY (Windows):
```bash
ssh your_username@live_server_ip
- eg. ssh root@1**.**9.3*.*6 -p 22

```
- your_username: This is the username you use to log into your live server.
- live_server_ip: This is the IP address of your live server.
You'll be prompted to enter your password for the server.

##### 2. Navigate to the Directory Containing the SQL File
Once you're logged in, navigate to the directory where you transferred the "myDb.sql" file. You can use the cd command to change directories.
```bash
cd /path/to/destination/
```
##### 3. Import the SQL File into the MySQL Database
```bash
mysql -u your_mysql_username -p your_live_database_name < myDbLocal.sql
```
Here's a breakdown of this command:
- "mysql": This is the MySQL command-line client used to interact with the MySQL server.
- "-u" your_mysql_username: Replace your_username with your MySQL username.
- "-p": This flag tells MySQL to prompt you for your MySQL password.
- "your_live_database_name": Replace this with the name of the database on your live server where you want to import the data.
- "<" myDbLocal.sql: The < symbol is used to tell MySQL to take the contents of myDbLocal.sql and execute them on your_live_database.

##### Example:
Let’s say your MySQL username is "root", your MySQL password is "password123", and the database on your live server is also named "myDbLive" and local database name is myDb.sql

```bash
mysql -u root -p myDbLive < myDbLocal.sql

```
  

