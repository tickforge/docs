---
type: docs
title: Player
---

# Player

The `player` block configures the player leveling system.

## Syntax

```tfs
player {
  xp_per_level: 100
}
```

## Properties

| Property | Type | Required | Default | Description |
|----------|------|----------|---------|-------------|
| `xp_per_level` | number | No | `100` | XP needed to gain a level |

## Leveling Formula

The XP required for each level increases:

```
XP for level N = xp_per_level * N
```

With `xp_per_level: 100`:
- Level 1: 100 XP
- Level 2: 200 XP
- Level 3: 300 XP
- etc.

## Gaining XP

XP is earned through:

### Actions

```tfs
action click {
  name: "Click"
  produces: 1 gold
  grants_xp: 1  # Gain 1 XP per click
}
```

### Achievements

```tfs
achievement milestone {
  name: "First Milestone"
  requires: 100 gold
  grants_xp: 50  # Bonus XP when unlocked
}
```

### Cheats

```tfs
cheat levelup {
  code: "levelup"
  grants_xp: 500
}
```

## Level Requirements

Player level can be used as a requirement for content:

```tfs
generator advanced_miner {
  name: "Advanced Miner"
  cost: 1000 gold
  produces: 10 gold
  requires: level 5  # Must be level 5 to purchase
}

upgrade super_click {
  name: "Super Click"
  cost: 500 gold
  requires: level 3
  effect: add click 5
}
```

## Display

The player's level and XP progress are shown in the top-right of the game header.

## Example

```tfs
player {
  xp_per_level: 50  # Faster leveling
}

action grind {
  name: "Grind"
  produces: 1 gold
  grants_xp: 2  # 2 XP per action
}

achievement first_level {
  name: "Level Up!"
  description: "Reach level 2"
  requires: level 2
  grants_xp: 25
}
```
