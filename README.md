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

