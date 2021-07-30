---
title: "Oracle DB"
description: "xo Oracle Database Support Reference"
date: 2021-06-25T11:23:19Z
lastmod: 2021-06-25T11:23:19Z
draft: false
images: []
menu:
  docs:
    parent: "reference"
weight: 60
toc: true
---

### Oracle Database

### Type Conversion Table

| SQL Type         | Go Type   | Go Nullable Type |
|------------------|-----------|------------------|
| BOOL             | bool      | sql.NullBool     |
| BLOB             | []byte    | []byte           |
| CHAR             | string    | sql.NullString   |
| CHARACTER        | string    | sql.NullString   |
| CLOB             | string    | sql.NullString   |
| DATE             | time.Time | sql.NullTime     |
| DOUBLE PRECISION | float64   | sql.NullFloat64  |
| DECIMAL          | int       | sql.NullInt64    |
| FLOAT            | float64   | sql.NullFloat64  |
| INT              | int       | sql.NullInt64    |
| INTEGER          | int       | sql.NullInt64    |
| LONGRAW          | []byte    | []byte           |
| NCHAR            | string    | sql.NullString   |
| NCLOB            | string    | sql.NullString   |
| NUMBER           | int64     | sql.NullInt64    |
| NUMERIC          | int       | sql.NullInt64    |
| NVARCHAR2        | string    | sql.NullString   |
| RAW              | []byte    | []byte           |
| REAL             | float64   | sql.NullFloat64  |
| ROWID            | string    | sql.NullString   |
| SMALLINT         | int       | sql.NullInt64    |
| TIMESTAMP\*      | time.Time | sql.NullTime     |
| VARCHAR          | string    | sql.NullString   |
| VARCHAR2         | string    | sql.NullString   |
| XMLTYPE          | []byte    | []byte           |
