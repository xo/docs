---
title: "Enums"
description: "Working with Enums in xo"
date: 2021-06-26T09:05:17Z
lastmod: 2021-06-26T09:05:17Z
draft: false
images: []
menu:
  docs:
    parent: "reference"
weight: 15
toc: true
---

## Enums

`xo` has full support for Enum types in PostgreSQL and MySQL. This page will
cover in detail how to create your own enum types and using them with `xo`.

```sql
CREATE TYPE book_type AS ENUM VALUES ('FICTION', 'NONFICTION')
```

```go
// Implementation details hidden for all functions

type BookType uint16
const (
  BookTypeFiction BookType = 1
  BookTypeNonfiction BookType = 2
)

func (bt BookType) String() string
func (bt BookType) MarshalText() ([]byte, error)
func (bt *BookType) UnmarshalText(buf []byte) error
func (bt BookType) Value() (driver.Value, error)
func (bt *BookType) Scan(v interface{}) error

type ErrInvalidBookType string
func (err ErrInvalidBookType) Error() string
```
