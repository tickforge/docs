---
type: docs
title: Items & Inventory
---

# Items & Inventory

Items are physical objects that occupy inventory slots.

## Inventory Declaration

First, enable inventory:

```tfs
inventory {
  slots: 28
}
```

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `slots` | number | `28` | Number of inventory slots |

## Item Syntax

```tfs
item identifier {
  name: "Display Name"
  icon: "X"
  description: "Item description"
  stackable: 1
  value: 0
}
```

## Item Properties

| Property | Type | Required | Default | Description |
|----------|------|----------|---------|-------------|
| `name` | string | Yes | - | Display name |
| `icon` | string | Yes | - | Icon/emoji |
| `description` | string | No | - | Tooltip text |
| `stackable` | number | No | `1` | `1` = stackable, `0` = unique |
| `value` | number | No | `0` | Base sell value |

## Stackable vs Non-Stackable

### Stackable Items

```tfs
item oak_log {
  name: "Oak Log"
  icon: "🪵"
  stackable: 1  # Multiple can occupy one slot
  value: 10
}
```

### Non-Stackable Items

```tfs
item bronze_sword {
  name: "Bronze Sword"
  icon: "🗡️"
  stackable: 0  # Each takes its own slot
  value: 100
}
```

## Obtaining Items

### From Nodes

```tfs
node oak_tree {
  name: "Oak Tree"
  location: forest
  gives: 1 oak_log
  cooldown: 3000
}
```

### From Recipes

```tfs
recipe bronze_bar {
  name: "Bronze Bar"
  consumes: 1 copper_ore, 1 tin_ore
  produces: 1 bronze_bar
}
```

### From Enemy Drops

```tfs
enemy goblin {
  name: "Goblin"
  location: forest
  drops: 1 bones 1.0       # 100% drop
  drops: 5 gold_coins 0.5  # 50% chance
}
```

## Bank Storage

Enable bank for extra storage:

```tfs
bank {
  slots: 800
}
```

Items can be deposited/withdrawn via the Bank button.

## Example

```tfs
inventory {
  slots: 28
}

bank {
  slots: 400
}

item copper_ore {
  name: "Copper Ore"
  icon: "🪨"
  description: "Raw copper ore"
  stackable: 1
  value: 5
}

item tin_ore {
  name: "Tin Ore"
  icon: "�ite"
  description: "Raw tin ore"
  stackable: 1
  value: 5
}

item bronze_bar {
  name: "Bronze Bar"
  icon: "🟫"
  description: "A bronze ingot"
  stackable: 1
  value: 25
}
```

## Display

- Inventory appears in the Inventory tab
- Items show icon, name, and quantity (if stackable)
- Bank accessible via header button
