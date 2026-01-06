---
type: docs
title: Language Reference
weight: 2
bookCollapseSection: true
---

# TickForge Language Reference

Complete documentation for the TickForge scripting language.

## Syntax Overview

TickForge uses a block-based syntax:

```tfs
# This is a comment

keyword identifier {
  property: value
  another_property: "string value"
  numeric_property: 100
}
```

### Value Types

| Type | Example | Description |
|------|---------|-------------|
| String | `"Hello World"` | Text in double quotes |
| Number | `100`, `1.5` | Integers or decimals |
| Identifier | `gold`, `my_resource` | Names (letters, numbers, underscores) |
| Amount | `10 gold` | Number followed by resource/item ID |
| Requirement | `level 5`, `10 gold` | Level or count requirement |
| Effect | `multiply miner 2` | Modification effect |

### Comments

```tfs
# Single line comment

# Multi-line comments use
# multiple single-line comments
```
