---
title: "Connection Strings"
description: "Connecting to your database with XO"
lead: "Connecting to your database with XO"
date: 2021-06-25T11:23:25Z
lastmod: 2021-06-25T11:23:25Z
draft: false
images: []
menu: 
  docs:
    parent: "getting started"
weight: 30
toc: true
---

## Connection Strings

Creating a connection string to your database can become confusing, especially
with all of the different formats that databases use. To help reduce
complexity, XO uses [dburl →](https://github.com/xo/dburl).

`dburl` provides a standard, URL style mechanism for parsing and opening SQL
database connection strings.

### How it works

Database connection URLs supported by XO are all in the same form:

```url
protocol+transport://user:pass@host/dbname?opt1=a&opt2=b
protocol:/path/to/file
```

Where:

| Component          | Description                                                                          |
|:------------------:|:-------------------------------------------------------------------------------------|
| protocol           | driver name or alias (see below)                                                     |
| transport          | "tcp", "udp", "unix" or driver name (odbc/oleodbc)                                   |
| user               | username                                                                             |
| pass               | password                                                                             |
| host               | host                                                                                 |
| dbname<sup>*</sup> | database, instance, or service name/ID to connect to                                 |
| ?opt1=[value]      | additional database driver options (see respective SQL driver for available options) |


{{< alert icon="💡" text=`<sup>*</sup>For Microsoft SQL Server, /dbname can be
/instance/dbname, where /instance is optional. For Oracle Database, /dbname is
of the form /service/dbname where /service is the service name or SID, and
/dbname is optional.examples.` />}}

To connect to your database with XO, here are the allowed protocols and driver names:

| Database (scheme/driver)         | Protocol Aliases                    |
|----------------------------------|-------------------------------------|
| PostgreSQL (postgres)            | pg, postgresql, pgsql               |
| MySQL (mysql)                    | my, maria                           |
| SQLite3 (sqlite3)                | sq, sqlite, file                    |
| Oracle Database (oracle)         | or, ora, oracle                     |
| Microsoft SQL Server (sqlserver) | ms, mssql                           |

### Examples

```url
postgres://user:pass@localhost/dbname
pg://user:pass@localhost/dbname?sslmode=disable
mysql://user:pass@localhost/dbname
mysql:/var/run/mysqld/mysqld.sock
sqlserver://user:pass@remote-host.com/dbname
mssql://user:pass@remote-host.com/instance/dbname
ms://user:pass@remote-host.com:port/instance/dbname?keepAlive=10
oracle://user:pass@somehost.com/sid
sqlite:/path/to/file.db
file:myfile.sqlite3?loc=auto
odbc+postgres://user:pass@localhost:port/dbname?option1=
```

To learn more about `dburl`, or to use it in your own project, check out its
[GitHub →](https://github.com/xo/dburl).
