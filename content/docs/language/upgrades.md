---
type: docs
title: Upgrades
---

# Upgrades

Upgrades are one-time purchases that permanently modify game elements.

## Syntax

```tfs
upgrade identifier {
  name: "Display Name"
  description: "Description text"
  cost: amount resource
  requires: requirement
  effect: effect_type target value
}
```

## Properties

| Property | Type | Required | Default | Description |
|----------|------|----------|---------|-------------|
| `name` | string | Yes | - | Display name |
| `description` | string | No | - | Description text |
| `cost` | amount | Yes | - | Purchase cost |
| `requires` | requirement | No | - | Unlock requirement |
| `effect` | effect | No | - | What the upgrade does |

## Effects

### Multiply

Multiplies a generator's output:

```tfs
upgrade double_miners {
  name: "Efficient Miners"
  description: "Miners produce 2x gold"
  cost: 500 gold
  effect: multiply miner 2
}
```

### Add

Adds to an action's output:

```tfs
upgrade better_click {
  name: "Better Clicking"
  description: "+1 gold per click"
  cost: 100 gold
  effect: add click 1
}
```

## Requirements

### Level Requirement

```tfs
upgrade advanced_tech {
  name: "Advanced Technology"
  cost: 1000 gold
  requires: level 5
  effect: multiply miner 2
}
```

### Generator Count Requirement

```tfs
upgrade miner_upgrade {
  name: "Mining Expertise"
  description: "Requires 10 miners"
  cost: 500 gold
  requires: 10 miner
  effect: multiply miner 2
}
```

## Examples

### Tiered Upgrades

```tfs
upgrade click_1 {
  name: "Iron Fingers"
  description: "+1 gold per click"
  cost: 50 gold
  effect: add click 1
}

upgrade click_2 {
  name: "Steel Fingers"
  description: "+2 gold per click"
  cost: 500 gold
  requires: level 3
  effect: add click 2
}

upgrade click_3 {
  name: "Diamond Fingers"
  description: "+5 gold per click"
  cost: 5000 gold
  requires: level 7
  effect: add click 5
}
```

### Generator Upgrades

```tfs
upgrade cursor_1 {
  name: "Reinforced Finger"
  description: "Cursors are 2x efficient"
  cost: 100 cookies
  requires: 1 cursor
  effect: multiply cursor 2
}

upgrade cursor_2 {
  name: "Ambidextrous"
  description: "Cursors are 2x efficient"
  cost: 500 cookies
  requires: 10 cursor
  effect: multiply cursor 2
}
```

## Display

Upgrades appear in the right panel. Once purchased, they disappear from the list.
