---
type: docs
title: Language Reference
weight: 2
bookCollapseSection: true
---

# TickForge Language Reference

Complete documentation for the TickForge scripting language.

## Table of Contents

### Core
- [Game Declaration](game) - Game metadata, themes, and settings
- [Resources](resources) - Defining accumulatable values
- [Player](player) - Player leveling system

### Gameplay
- [Actions](actions) - Clickable buttons
- [Generators](generators) - Automatic production
- [Upgrades](upgrades) - One-time purchases
- [Achievements](achievements) - Milestones and rewards

### RPG Systems
- [Skills](skills) - Skill-based progression
- [Items & Inventory](items) - Item management
- [Locations & Nodes](locations) - World and gathering
- [Combat](combat) - Enemies and fighting
- [Recipes](recipes) - Crafting system
- [Equipment](equipment) - Gear and bonuses
- [Bank](bank) - Item storage

### Meta
- [Themes](themes) - Visual customization
- [Cheats](cheats) - Cheat codes
- [Endgame & Credits](endgame) - Win conditions

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
