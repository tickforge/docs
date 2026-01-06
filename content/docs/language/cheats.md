---
type: docs
title: Cheats
---

# Cheats

Add cheat codes for testing or fun Easter eggs.

## Syntax

```tfs
cheat identifier {
  code: "cheatcode"
  description: "What the cheat does"
  gives: amount resource
  grants_xp: number
  one_time: 0 or 1
}
```

## Properties

| Property | Type | Required | Default | Description |
|----------|------|----------|---------|-------------|
| `code` | string | Yes | - | The cheat code to type |
| `description` | string | No | - | Description (shown after use) |
| `gives` | amount | No | - | Resources to give |
| `grants_xp` | number | No | `0` | XP to grant |
| `one_time` | number | No | `0` | `1` = can only use once |

## Usage

Players type cheat codes directly while playing:
1. Just start typing the code (no input field needed)
2. Matching codes activate automatically
3. Feedback shown on successful activation

## Examples

### Resource Cheats

```tfs
cheat motherlode {
  code: "motherlode"
  description: "Gain 1 million gold!"
  gives: 1000000 gold
  one_time: 0  # Can use repeatedly
}

cheat rosebud {
  code: "rosebud"
  description: "Gain 10,000 gold"
  gives: 10000 gold
  one_time: 0
}
```

### XP Cheats

```tfs
cheat levelup {
  code: "levelup"
  description: "Gain 500 XP!"
  gives: 0 gold  # Required but can be 0
  grants_xp: 500
  one_time: 0
}

cheat maxlevel {
  code: "maxlevel"
  description: "Gain massive XP!"
  gives: 0 gold
  grants_xp: 100000
  one_time: 1  # Only works once
}
```

### One-Time Cheats

```tfs
cheat unlock_all {
  code: "opensesame"
  description: "Unlock everything! (one-time)"
  gives: 10000000000 gold
  grants_xp: 10000
  one_time: 1
}
```

### Combination Cheats

```tfs
cheat boost {
  code: "powerup"
  description: "Resources and XP boost!"
  gives: 50000 gold
  grants_xp: 250
  one_time: 0
}
```

cheat konami {
  code: "uuddlrlrba"
  description: "30 lives! (metaphorically)"
  gives: 30000 gold
  grants_xp: 30
  one_time: 1
}
```

## Notes

- Codes are case-sensitive
- Codes activate as soon as typed (no enter needed)
- One-time cheats tracked in save data
- Consider balancing: too powerful cheats may reduce engagement
