---
title: "Overview"
description: "An overview of xo and its features"
date: 2020-10-06T08:48:57+00:00
lastmod: 2020-10-06T08:48:57+00:00
draft: false
images: []
menu:
  docs:
    parent: "getting started"
weight: 10
toc: true
---

## Overview

`xo` is a command-line tool to generate _idiomatic_ code for different languages
code based on a database schema or a custom query.

### Supported languages

At the moment, `xo` supports generating code just for [Go](https://golang.org).
`xo` can also generate a JSON Schema file from your DB, and
[GraphViz](http://graphviz.org/) diagrams.

### Features

- Type-safe and idiomatic Go code.
- Logging all DB operations
- Working with transactions
- Generated types/objects for tables and views
- Type-safe CRUD operations
- Type-safe functions/methods for primary keys, indexes, and foreign keys
- Fully customisable templates
- Automatic primary keys support
- Type-safe code generation from your custom queries

**Go-specific:**

- \*sql.DB integration
- Supply custom Go types for SQL data types
- Generate code with and without context

### Databases

`xo` can generate types for tables, enums, stored procedures, and custom SQL
queries for the following languages:

- [PostgreSQL →]({{< relref "databases#postgresql" >}})
- [MySQL →]({{< relref "databases#mysql" >}})
- [Oracle →]({{< relref "databases#oracle" >}})
- [Microsoft SQL Server →]({{< relref "databases#miscroft-sql-server" >}})
- [SQLite3 →]({{< relref "databases#sqlite3" >}})

For more info about supported databases, visit the [databases page →]({{<
relref "databases" >}})

_xo/xo — hugs and kisses from your database_.
