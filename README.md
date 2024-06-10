# SQL-Essentials
SQL-Essentials


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

