---
title: "PostgreSQL"
description: "xo PostgreSQL Support Reference"
date: 2021-06-25T11:23:19Z
lastmod: 2021-06-25T11:23:19Z
draft: false
images: []
menu:
  docs:
    parent: "reference"
weight: 20
toc: true
---

## PostgreSQL

### Enum types

`xo` has full support for Enum types in PostgreSQL. Learn more here:

[Working with Enums →]({{% relref "enums" %}})

### Type Conversion Table

| SQL Type          | Go Type                | Go Nullable Type         |
|-------------------|------------------------|--------------------------|
| Enum              | (Custom type)          | (Custom type)(0)         |
| BIGINT            | int64                  | sql.NullInt64            |
| BIGSERIAL         | int64                  |                          |
| BIT               | uint8                  | \*uint8                  |
| BIT VARYING       | []byte                 | []byte                   |
| BOOL              | bool                   | sql.NullBool             |
| BOOLEAN           | bool                   | sql.NullBool             |
| BPCHAR            | string                 | sql.NullString           |
| BYTEA             | []byte                 | []byte                   |
| CHAR              | string                 | sql.NullString           |
| CHARACTER         | string                 | sql.NullString           |
| CHARACTER VARYING | string                 | sql.NullString           |
| DATE              | time.Time              | time.NullTime            |
| DECIMAL           | float64                | sql.NullFloat64          |
| DOUBLE PRECISION  | float64                | sql.NullFloat64          |
| INET              | string                 | sql.NullString           |
| INT               | int                    | sql.NullInt64            |
| INTEGER           | int                    | sql.NullInt64            |
| INTERVAL          | []byte                 | []byte                   |
| JSON              | []byte                 | []byte                   |
| JSONB             | []byte                 | []byte                   |
| MONEY             | string                 | sql.NullString           |
| NUMERIC           | float64                | sql.NullFloat64          |
| REAL              | float32                | sql.NullFloat64          |
| SERIAL            | int                    | N/A                      |
| SMALLINT          | int16                  | sql.NullInt64            |
| SMALLSERIAL       | int16                  | N/A                      |
| TEXT              | string                 | sql.NullString           |
| TIME\*            | time.Time              | sql.NullTime             |
| UUID<sup>1</sup>  | github.com/google/UUID | \*github.com/google/UUID |
| VARCHAR           | string                 | sql.NullString           |
| XML               | []byte                 | []byte                   |

{{< alert icon="💡" text=`<sup>1</sup> The UUID type is configurable with the
--go-uuid flag.` />}}
