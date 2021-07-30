---
title: "SQLite3"
description: "xo SQLite3 Support Reference"
date: 2021-06-25T11:23:19Z
lastmod: 2021-06-25T11:23:19Z
draft: false
images: []
menu:
  docs:
    parent: "reference"
weight: 40
toc: true
---

### SQLite3

### Type Conversion Table


| SQL Type          | Go Type   | Go Nullable Type |
|-------------------|-----------|------------------|
| BIGINT            | int64     | sql.NullInt64    |
| BLOB              | []byte    | []byte           |
| BOOL              | boolean   | sql.NullBool     |
| BOOLEAN           | boolean   | sql.NullBool     |
| CHARACTER         | string    | sql.NullString   |
| CLOB              | string    | sql.NullString   |
| DATE\*            | time.Time | sql.NullTime     |
| DECIMAL           | float64   | sql.NullFloat64  |
| DOUBLE            | float64   | sql.NullFloat64  |
| FLOAT             | float64   | sql.NullFloat64  |
| INT               | int       | sql.NullInt64    |
| INTEGER           | int       | sql.NullInt64    |
| MEDIUMINT         | int       | sql.NullInt64    |
| NATIVE CHARACTER  | string    | sql.NullString   |
| NCHAR             | string    | sql.NullString   |
| NUMERIC           | float64   | sql.NullFloat64  |
| NVARCHAR          | string    | sql.NullString   |
| REAL              | float64   | sql.NullFloat64  |
| SAMLLINT          | int       | sql.NullInt64    |
| TEXT              | string    | sql.NullString   |
| TIME              | Time      | \*Time           |
| TIMESTAMP\*       | Time      | \*Time           |
| TINYINT           | int       | sql.NullInt64    |
| VARCHAR           | string    | sql.NullString   |
| VARYING CHARACTER | string    | sql.NullString   |
