# SQL Cheat Sheet

## Table Management

- **Create Table**
  ```sql
  CREATE TABLE table_name (
      column1 datatype,
      column2 datatype,
      ...
  );
  ```
- **Drop Table**
  ```sql
  DROP TABLE table_name;
  ```
- **Alter Table (Add Column)**
  ```sql
  ALTER TABLE table_name ADD COLUMN new_column datatype;
  ```

## Data Manipulation

- **Insert Data**
  ```sql
  INSERT INTO table_name (column1, column2) VALUES ('value1', 'value2');
  ```
- **Select Data**
  ```sql
  SELECT column1, column2 FROM table_name WHERE condition;
  ```
- **Update Data**
  ```sql
  UPDATE table_name SET column1 = 'new_value' WHERE condition;
  ```
- **Delete Data**
  ```sql
  DELETE FROM table_name WHERE condition;
  ```

## Filtering & Sorting

- **WHERE Clause**
  ```sql
  SELECT * FROM table_name WHERE column = 'value';
  ```
- **ORDER BY**
  ```sql
  SELECT * FROM table_name ORDER BY column ASC|DESC;
  ```
- **LIMIT**
  ```sql
  SELECT * FROM table_name LIMIT 10;
  ```

## Joins

- **Inner Join**
  ```sql
  SELECT * FROM table1
  INNER JOIN table2 ON table1.column = table2.column;
  ```
- **Left Join**
  ```sql
  SELECT * FROM table1
  LEFT JOIN table2 ON table1.column = table2.column;
  ```

## Aggregation

- **COUNT, SUM, AVG, MIN, MAX**
  ```sql
  SELECT COUNT(*), SUM(column), AVG(column), MIN(column), MAX(column)
  FROM table_name;
  ```
- **GROUP BY**
  ```sql
  SELECT column, COUNT(*) FROM table_name GROUP BY column;
  ```

## Other Useful Commands

- **Show Tables**
  ```sql
  -- PostgreSQL
  \dt
  -- MySQL/SQLite
  SHOW TABLES;
  ```
- **Describe Table**
  ```sql
  -- PostgreSQL
  \d table_name
  -- MySQL/SQLite
  DESCRIBE table_name;
  ```
- **Show Databases**
  ```sql
  -- PostgreSQL
  \l
  -- MySQL/SQLite
  SHOW DATABASES;
  ```

## Comments

- **Single-line comment**
  ```sql
  -- This is a comment
  ```
- **Multi-line comment**
  ```sql
  /* This is a
     multi-line comment */
  ```

## Useful PostgreSQL Meta-Commands (psql)

- List users: `\du`
- List databases: `\l`
- List tables: `\dt`
- Describe table: `\d table_name`
- Quit psql: `\q`

---

For more, see the official documentation or your database's help system.
