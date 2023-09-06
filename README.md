# Chinook

The Chinook database is a sample database often used in tutorials, documentation, and examples for learning and demonstrating database management systems (DBMS) and SQL. It's a fictional database representing a music store or digital media store, and it typically contains tables and data related to music sales, customers, employees, artists, albums, and tracks.

This repository provide the same SQL script to create a SQLite or a DuckDB database. This SQL script `chinook.sql` was adopted from [`Chinook_Sqlite.sql`](https://github.com/lerocha/chinook-database/blob/master/ChinookDatabase/DataSources/Chinook_Sqlite.sql)

## Differences between Sqlite3 and DuckDB

1. SQLite supports the use of double quotatios ("") and square brackets ([]) to enclose table and field names with whitespaces and capital letter. DuckDB only support the former.

2. In SQLite, users can create a table with a foreign key constraint that references another table not yet in existence during table creation. SQLite does not verify the referenced table's existence when creating the foreign key constraint. However, it enforces foreign key constraints during data insertion or updates. DuckDB behaves more in alignment with conventional relational database systems, requiring referenced tables to exist at the time foreign key constraints are created.

3. SQLite permits users to drop a table even if it contains one or more fields serving as foreign keys for other tables. In contrast, DuckDB disallows this action.

## Database Creation

### Create a SQLite database `chinook.sqlite`

**Dos/Unix/Linix/MacOS Command Prompt**
```bash
sqlite3 chinook.sqlite < chinook.sql
```
**PowerShell**
```bash
Get-Content .\chinook.sql | sqlite3 chinook.sqlite
```

### Create a DuckDB database `chinook.duckdb`

**Dos/Unix/Linix/MacOS Command Prompt**
```bash
duckdb chinook.duckdb < chinook.sql
```
**PowerShell**
```bash
Get-Content .\chinook.sql | duckdb chinook.duckdb
```
