---
title: "MySQL"
description: "xo MySQL Support Reference"
date: 2021-06-25T11:23:19Z
lastmod: 2021-06-25T11:23:19Z
draft: false
images: []
menu:
  docs:
    parent: "reference"
weight: 30
toc: true
---

### MySQL + MariaDB

### Enum types

`xo` has full support for Enum types in PostgreSQL. Learn more here:

[Working with Enums →]({{% relref "enums" %}})

### Type Conversion Table

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
