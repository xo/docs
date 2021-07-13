---
title: "Databases"
description: "XO Database support reference"
date: 2021-06-25T11:23:19Z
lastmod: 2021-06-25T11:23:19Z
draft: false
images: []
menu:
  docs:
    parent: "getting started"
weight: 30
toc: true
---

## Databases

At the moment, XO supports 5 major relational databases:

1. [PostgreSQL](https://www.postgresql.org/)
2. [MySQL](https://www.mysql.com/)
3. [SQLite3](https://sqlite.org/)
4. [Microsoft SQL Server](https://www.microsoft.com/en-us/sql-server/)
5. [Oracle Database](https://www.oracle.com/database/)

|                          | PostgreSQL | MySQL | SQLite | SQL Server | Oracle Database |
| ------------------------ | :--------: | :---: | :----: | :--------: | :-------------: |
| Tables                   | ✅         | ✅    | ✅     | ✅         | ✅              |
| Views                    | ✅         | ✅    | ✅     | ✅         | ✅              |
| Primary Keys             | ✅         | ✅    | ✅     | ✅         | ✅              |
| Sequences                | ✅         | ✅    | ✅     | ✅         | ✅              |
| Foreign Key              | ✅         | ✅    | ✅     | ✅         | ✅              |
| Indexes                  | ✅         | ✅    | ✅     | ✅         | ✅              |
| Stored Procs<sup>1</sup> | ✅         | ✅    | ✅     | ✅         | ✅              |
| ENUM types               | ✅         | ✅    |        |            |                 |
| Custom types             | ✅         |       |        |            |                 |

{{< alert icon="💡" text=`<sup>1</sup> Currently, stored procedures will only
return up to one parameter back. Support for multiple parameter return is
coming soon.` />}}

### Type conversion

XO aims to replicate the output from the databases as closely as possible.
Databases support different types under different names, however. Here is the
default mapping for all of the types that each database supports.

{{< alert icon="👉" text=`At the moment, UUID and numeric types are
configurable. Support to configure all types to your own types is coming soon.`
/>}}

### PostgreSQL

##### Enum types

XO has full support for Enum types in PostgreSQL. Learn more here:

[Working with Enums →]({{% relref "enums" %}})

---

| SQL Type          | Go Type                | Go Nullable Type        |
|-------------------|------------------------|-------------------------|
| Enum              | (Custom type)          | (Custom type)(0)        |
| BIGINT            | int64                  | sql.NullInt64           |
| BIGSERIAL         | int64                  |                         |
| BIT               | uint8                  | *uint8                  |
| BIT VARYING       | []byte                 | []byte                  |
| BOOL              | bool                   | sql.NullBool            |
| BOOLEAN           | bool                   | sql.NullBool            |
| BPCHAR            |  string                | sql.NullString          |
| CHAR              | string                 | sql.NullString          |
| CHARACTER         | string                 | sql.NullString          |
| CHARACTER VARYING | string                 | sql.NullString          |
| DATE              | time.Time              | time.NullTime           |
| DECIMAL           | float64                | sql.NullFloat64         |
| DOUBLE PRECISION  | float64                | sql.NullFloat64         |
| INET              | string                 | sql.NullString          |
| INT               | int                    | sql.NullInt64           |
| INTEGER           | int                    | sql.NullInt64           |
| INTERVAL          | []byte                 | []byte                  |
| JSON              | []byte                 | []byte                  |
| JSONB             | []byte                 | []byte                  |
| MONEY             | string                 | sql.NullString          |
| NUMERIC           | float64                | sql.NullFloat64         |
| REAL              | float32                | sql.NullFloat64         |
| SERIAL            | int                    |                         |
| SMALLINT          | int16                  | sql.NullInt64           |
| SMALLSERIAL       | int16                  |                         |
| TEXT              | string                 | sql.NullString          |
| TIME              | time.Time              | sql.NullTime            |
| TIMESTAMP         | time.Time              | sql.NullTime            |
| TIMESTAMPTZ       | time.Time              | sql.NullTime            |
| TIMETZ            | time.Time              | sql.NullTime            |
| UUID              | github.com/google/UUID | *github.com/google/UUID |
| VARCHAR           | string                 | sql.NullString          |
| XML               | []byte                 | []byte                  |

### MySQL

| SQL Type         | Go Type       | Go Nullable Type |
|------------------|---------------|------------------|
| BIGINT           | int64         | sql.NullInt64    |
| BINARY           | []byte        | []byte           |
| BIT              | bool          | sql.NullBool     |
| BLOB             | []byte        | []byte           |
| CHAR             | string        | sql.NullString   |
| DATE             | time.Time     | sql.NullTime     |
| DATETIME         | time.Time     | sql.NullTime     |
| DEC              | float64       | sql.NullFloat64  |
| FIXED            | float64       | sql.NullFloat64  |
| DECIMAL          | float64       | sql.NullFloat64  |
| DOUBLE PRECISION | float64       | sql.NullFloat64  |
| ENUM             | (Custom Type) | (Custom Type)(0) |
| FLOAT            | float32       | sql.NullFloat64  |
| INT              | int           | sql.NullInt64    |
| INTEGER          | int           | sql.NullInt64    |
| JSON             | string        | sql.NullString   |
| LONGBLOB         | []byte        | []byte           |
| LONGTEXT         | string        | sql.NullString   |
| MEDIUMBLOB       | []byte        | []byte           |
| MEDIUMINT        | int           | sql.NullInt64    |
| MEDIUMTEXT       | string        | sql.NullString   |
| NUMERIC          | float64       | sql.NullFloat64  |
| REAL             | float32       | sql.NullFloat64  |
| SET              | []byte        | []byte           |
| SMALLINT         | int16         | sql.NullInt64    |
| TEXT             | string        | sql.NullString   |
| TIME             | string        | sql.NullString   |
| TIMESTAMP        | time.Time     |                  |
| TINYBLOB         | []byte        | []byte           |
| TINYINT          | int8          | sql.NullInt64    |
| TINYTEXT         | string        | sql.NullString   |
| VARBINARY        | []byte        | []byte           |
| VARCHAR          | string        | sql.NullString   |
| YEAR             | int16         | sql.NullInt64    |

### SQLite3

| SQL Type                   | Go Type   | Go Nullable Type |
|----------------------------|-----------|------------------|
| BIGINT                     | int64     | sql.NullInt64    |
| BLOB                       | []byte    | []byte           |
| BOOL                       | boolean   | sql.NullBool     |
| BOOLEAN                    | boolean   | sql.NullBool     |
| CHARACTER                  | string    | sql.NullString   |
| CLOB                       | string    | sql.NullString   |
| DATE                       | time.Time | sql.NullTime     |
| DATETIME                   | time.Time | sql.NullTime     |
| DECIMAL                    | float64   | sql.NullFloat64  |
| DOUBLE                     | float64   | sql.NullFloat64  |
| FLOAT                      | float64   | sql.NullFloat64  |
| INT                        | int       | sql.NullInt64    |
| INTEGER                    | int       | sql.NullInt64    |
| MEDIUMINT                  | int       | sql.NullInt64    |
| NATIVE CHARACTER           | string    | sql.NullString   |
| NCHAR                      | string    | sql.NullString   |
| NUMERIC                    | float64   | sql.NullFloat64  |
| NVARCHAR                   | string    | sql.NullString   |
| REAL                       | float64   | sql.NullFloat64  |
| SAMLLINT                   | int       | sql.NullInt64    |
| TEXT                       | string    | sql.NullString   |
| TIME                       | time.Time | sql.NullTime     |
| TIMESTAMP                  | time.Time | sql.NullTime     |
| TIMESTAMP WITHOUT TIMEZONE | time.Time | sql.NullTime     |
| TIMESTAMP WITH TIMEZONE    | time.Time | sql.NullTime     |
| TIME WITH TIMEZONE         | time.Time | sql.NullTime     |
| TINYINT                    | int       | sql.NullInt64    |
| VARCHAR                    | string    | sql.NullString   |
| VARYING CHARACTER          | string    | sql.NullString   |

### Microsoft SQL Server

| SQL Type       | Go Type   | Go Nullable Type |
|----------------|-----------|------------------|
| bigint         | int64     | sql.NullInt64    |
| binary         | []byte    | []byte           |
| bit            | bool      | sql.NullBool     |
| char           | string    | sql.NullString   |
| date           | time.Time | sql.NullTime     |
| datetime       | time.Time | sql.NullTime     |
| datetime2      | time.Time | sql.NullTime     |
| datetimeoffset | time.Time | sql.NullTime     |
| decimal        | float64   | sql.NullFloat64  |
| float          | float64   | sql.NullFloat64  |
| image          | []byte    | []byte           |
| int            | int       | sql.NullInt64    |
| money          | string    | sql.NullString   |
| nchar          | string    | sql.NullString   |
| ntext          | string    | sql.NullString   |
| numeric        | float64   | sql.NullFloat64  |
| nvarchar       | string    | sql.NullString   |
| real           | float32   | sql.NullFloat64  |
| smalldatetime  | time.Time | sql.NullTime     |
| smallint       | int16     | sql.NullInt64    |
| smallmoney     | string    | sql.NullString   |
| text           | string    | sql.NullString   |
| time           | time.Time | sql.NullTime     |
| tinyint        | bool      | sql.NullBool     |
| varbinary      | []byte    | []byte           |
| varchar        | string    | sql.NullTime     |
| xml            | []byte    | []byte           |

### Oracle Database
