---
title: "Microsoft SQL Server"
description: "xo Microsoft SQL Server Support Reference"
date: 2021-06-25T11:23:19Z
lastmod: 2021-06-25T11:23:19Z
draft: false
images: []
menu:
  docs:
    parent: "reference"
weight: 50
toc: true
---

## Microsoft SQL Server

### Type Conversion Table

| SQL Type       | Go Type   | Go Nullable Type |
|----------------|-----------|------------------|
| BIGINT         | int64     | sql.NullInt64    |
| BINARY         | []byte    | []byte           |
| BIT            | bool      | sql.NullBool     |
| CHAR           | string    | sql.NullString   |
| DATE\*         | time.Time | sql.NullTime     |
| DECIMAL        | float64   | sql.NullFloat64  |
| FLOAT          | float64   | sql.NullFloat64  |
| IMAGE          | []byte    | []byte           |
| INT            | int       | sql.NullInt64    |
| MONEY          | string    | sql.NullString   |
| NCHAR          | string    | sql.NullString   |
| NTEXT          | string    | sql.NullString   |
| NUMERIC        | float64   | sql.NullFloat64  |
| NVARCHAR       | string    | sql.NullString   |
| REAL           | float32   | sql.NullFloat64  |
| SMALLDATETIME  | time.Time | sql.NullTime     |
| SMALLINT       | int16     | sql.NullInt64    |
| SMALLMONEY     | string    | sql.NullString   |
| TEXT           | string    | sql.NullString   |
| TIME           | time.Time | sql.NullTime     |
| TINYINT        | bool      | sql.NullBool     |
| VARBINARY      | []byte    | []byte           |
| VARCHAR        | string    | sql.NullTime     |
| XML            | []byte    | []byte           |
