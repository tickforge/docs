---
type: docs
title: Achievements
---

# Achievements

Achievements are milestones that unlock automatically when conditions are met.

## Syntax

```tfs
achievement identifier {
  name: "Display Name"
  description: "Description text"
  requires: requirement
  grants_xp: number
}
```

## Properties

| Property | Type | Required | Default | Description |
|----------|------|----------|---------|-------------|
| `name` | string | Yes | - | Achievement name |
| `description` | string | No | - | Description text |
| `requires` | requirement | Yes | - | Unlock condition |
| `grants_xp` | number | No | `0` | XP reward when unlocked |

## Requirement Types

### Resource Amount

```tfs
achievement rich {
  name: "Getting Rich"
  description: "Accumulate 1000 gold"
  requires: 1000 gold
  grants_xp: 50
}
```

### Generator Count

```tfs
achievement miner_army {
  name: "Mining Army"
  description: "Own 10 miners"
  requires: 10 miner
  grants_xp: 25
}
```

### Player Level

```tfs
achievement leveled_up {
  name: "Level 10"
  description: "Reach level 10"
  requires: level 10
  grants_xp: 100
}
```

## Examples

### Resource Milestones

```tfs
achievement first_gold {
  name: "First Gold"
  description: "Earn your first gold"
  requires: 1 gold
  grants_xp: 10
}

achievement hundred_gold {
  name: "Coin Collector"
  description: "Earn 100 gold"
  requires: 100 gold
  grants_xp: 25
}

achievement thousand_gold {
  name: "Gold Hoarder"
  description: "Earn 1,000 gold"
  requires: 1000 gold
  grants_xp: 50
}

achievement million_gold {
  name: "Millionaire"
  description: "Earn 1,000,000 gold"
  requires: 1000000 gold
  grants_xp: 500
}
```

### Generator Milestones

```tfs
achievement first_miner {
  name: "First Employee"
  description: "Hire your first miner"
  requires: 1 miner
  grants_xp: 10
}

achievement ten_miners {
  name: "Small Business"
  description: "Employ 10 miners"
  requires: 10 miner
  grants_xp: 50
}

achievement hundred_miners {
  name: "Mining Corporation"
  description: "Employ 100 miners"
  requires: 100 miner
  grants_xp: 200
}
```

## Display

Achievements appear in the right panel below upgrades, showing:
- Locked achievements (grayed out with requirements)
- Unlocked achievements (highlighted)
