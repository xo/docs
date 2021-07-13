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
weight: 40
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

| Component          | Description                                          |
|:------------------:|:-----------------------------------------------------|
| protocol           | driver name or alias (see below)                     |
| transport          | "tcp", "udp", "unix" or driver name (odbc/oleodbc)   |
| user               | username                                             |
| pass               | password                                             |
| host               | host                                                 |
| dbname<sup>1</sup> | database, instance, or service name/ID to connect to |
| ?opt1=[value]      | additional database driver options                   |

{{< alert icon="💡" text=`<sup>1</sup> For Microsoft SQL Server,
<code>/dbname</code>, can be <code>/instance/dbname</code>, where
<code>/instance</code> is optional. For Oracle Database, <code>/dbname</code>
is of the form <code>/service/dbname</code> where <code>/service</code> is the
service name or SID, and <code>/dbname</code> is optional.` />}}

To connect to your database with XO, here are the allowed protocols and driver
names:

| Database (scheme/driver)         | Protocol Aliases     |
|----------------------------------|----------------------|
| PostgreSQL (postgres)            | pg, postgresql, pgsql|
| MySQL (mysql)                    | my, maria            |
| SQLite3 (sqlite3)                | sq, sqlite, file     |
| Oracle Database (oracle)         | or, ora, oracle      |
| Microsoft SQL Server (sqlserver) | ms, mssql            |

### Examples

{{% code
name="Connection Urls"
lang="url"
postgres=`postgres://user:pass@localhost/dbname
pg://user:pass@localhost/dbname?sslmode=disable`

mysql=`mysql://user:pass@localhost/dbname
mysql:/var/run/mysqld/mysqld.sock`

sqlite=`sqlite:/path/to/file.db
file:myfile.sqlite3?loc=auto`

sqlserver=`mssql://user:pass@remote-host.com/instance/dbname
ms://user:pass@remote-host.com:port/instance/dbname?keepAlive=10`

oracle=`oracle://user:pass@somehost.com/sid
or://user:pass@localhost/db1`
%}}

To learn more about `dburl`, or to use it in your own project, check out its
[GitHub →](https://github.com/xo/dburl).
