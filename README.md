# Chinook

The Chinook database is a sample database often used in tutorials, documentation, and examples for learning and demonstrating database management systems (DBMS) and SQL. It's a fictional database representing a music store or digital media store, and it typically contains tables and data related to music sales, customers, employees, artists, albums, and tracks.

This repository provide the same SQL script to create a SQLite or a DuckDB database. This SQL script `chinook.sql` was adopted from [`Chinook_Sqlite.sql`](https://github.com/lerocha/chinook-database/blob/master/ChinookDatabase/DataSources/Chinook_Sqlite.sql)

## Differences between Sqlite3 and DuckDB

1. SQLite support the use of double quotatios ("") and square brackets ([]) to enclose table and field names with whitespaces and capital letter. DuckDB only support the former.
2. SQLite allows users to create a table with a foreign key constraint that references another table that does not exist at the time of the table creation. SQLite does not check the existence of the referenced table when creating the foreign key constraint. However, SQLite does enforce foreign key constraints during inserting or updating of data. DuckDB's behavior is more in line with traditional relational database systems that require referenced tables to exist at the time foreign key constraints are created.
3. SQLite allows users to drop a table even if the table has one or more fields which are foreign keys of other tables. However, DUckDB disallow this.

## Database Creation

### Create a SQLite database: `chinook.sqlite`

```bash
sqlite3 chinook.sqlite < chinook.sql
```

### Create a DuckDB database: `chinook.duckdb`

```bash
duckdb chinook.duckdb < chinook.sql
```
