---
title: "Databases"
description: "xo Database support reference"
date: 2021-06-25T11:23:19Z
lastmod: 2021-06-25T11:23:19Z
draft: false
images: []
menu:
  docs:
    parent: "reference"
weight: 10
toc: true
---

## Databases

At the moment, `xo` supports 5 major relational databases:

|                          | PostgreSQL | MySQL | SQLite | SQL Server | Oracle |
| ------------------------ | :--------: | :---: | :----: | :--------: | :----: |
| | [Reference]({{% relref "postgres" %}}) | [Reference]({{% relref "mysql" %}}) | [Reference]({{% relref "sqlite3" %}}) | [Reference]({{% relref "sqlserver" %}}) | [Reference]({{% relref "oracle" %}}) |
| Custom Queries           | ✅         | ✅    | ✅     | ✅         | ✅     |
| Tables                   | ✅         | ✅    | ✅     | ✅         | ✅     |
| Views                    | ✅         | ✅    | ✅     | ✅         | ✅     |
| Primary Keys             | ✅         | ✅    | ✅     | ✅         | ✅     |
| Sequences                | ✅         | ✅    | ✅     | ✅         | ✅     |
| Foreign Key              | ✅         | ✅    | ✅     | ✅         | ✅     |
| Indexes                  | ✅         | ✅    | ✅     | ✅         | ✅     |
| Stored Procs<sup>1</sup> | ✅         | ✅    | ✅     | ✅         | ✅     |
| Stored Funcs<sup>1</sup> | ✅         | ✅    | ✅     | ✅         | ✅     |
| ENUM types               | ✅         | ✅    |        |            |        |
| Custom types             | ✅         |       |        |            |        |

{{< alert icon="💡" text=`<sup>1</sup> Currently, functions and procedures only
support non-cursor IN and OUT parameters. For MySQL, procedures that have out
parameters are not supported` />}}

## Drivers

`xo` is designed to work with most drivers, and to be compatible with
`database/sql` when targeting Go.

Here are the drivers that `xo` uses to generate output, and the libraries that
are tested and confirmed to work with `xo`.

| Database (driver)            | Package                                                                      |
|------------------------------|------------------------------------------------------------------------------|
| PostgreSQL (postgres)        | [github.com/lib/pq](https://github.com/lib/pq)                               |
| SQLite3 (sqlite3)            | [github.com/mattn/go-sqlite3](https://github.com/mattn/go-sqlite3)           |
| MySQL (mysql)                | [github.com/go-sql-driver/mysql](https://github.com/go-sql-driver/mysql)     |
| Microsoft SQL Server (mssql) | [github.com/denisenkom/go-mssqldb](https://github.com/denisenkom/go-mssqldb) |
| Oracle (go-ora)              | [github.com/sijms/go-ora](https://github.com/sijms/go-ora)                   |
| Oracle (godror) (tested)     | [github.com/godror/godror](https://github.com/godror/godror)                 |
