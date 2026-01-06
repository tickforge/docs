---
type: docs
title: Combat
---

# Combat

Add enemies and a combat system to your game.

## Enemy Syntax

```tfs
enemy identifier {
  name: "Display Name"
  description: "Description"
  icon: "X"
  location: location_id
  health: number
  max_hit: number
  attack_speed: ticks
  attack_level: number
  strength_level: number
  defence_level: number
  requires_skill: skill level
  drops: quantity item chance
  gives_xp: amount skill
  respawn_time: milliseconds
}
```

## Enemy Properties

| Property | Type | Required | Default | Description |
|----------|------|----------|---------|-------------|
| `name` | string | Yes | - | Display name |
| `description` | string | No | - | Description |
| `icon` | string | Yes | - | Icon/emoji |
| `location` | id | Yes | - | Where enemy spawns |
| `health` | number | Yes | - | Hit points |
| `max_hit` | number | Yes | - | Maximum damage per attack |
| `attack_speed` | number | No | `4` | Ticks between attacks |
| `attack_level` | number | No | `1` | Attack accuracy |
| `strength_level` | number | No | `1` | Damage bonus |
| `defence_level` | number | No | `1` | Defense rating |
| `requires_skill` | skill level | No | - | Combat skill requirement |
| `drops` | qty item chance | No | - | Loot (can have multiple) |
| `gives_xp` | amt skill | No | - | XP reward on kill |
| `respawn_time` | number | No | `5000` | Ms to respawn |

## Drop Syntax

```tfs
drops: quantity item chance
```

- `quantity` - Number of items dropped
- `item` - Item identifier
- `chance` - Drop rate from 0.0 to 1.0 (0.5 = 50%)

## Example Enemies

```tfs
enemy chicken {
  name: "Chicken"
  description: "A harmless chicken"
  icon: "🐔"
  location: lumbridge
  health: 3
  max_hit: 1
  attack_speed: 4
  attack_level: 1
  strength_level: 1
  defence_level: 1
  drops: 1 raw_chicken 1.0
  drops: 1 feather 1.0
  gives_xp: 12 attack
  gives_xp: 4 hitpoints
  respawn_time: 3000
}

enemy goblin {
  name: "Goblin"
  description: "A sneaky goblin"
  icon: "👺"
  location: forest
  health: 25
  max_hit: 3
  attack_speed: 4
  attack_level: 5
  strength_level: 5
  defence_level: 5
  requires_skill: attack 5
  drops: 1 bones 1.0
  drops: 10 gold_coins 0.5
  drops: 1 goblin_mail 0.1
  gives_xp: 25 attack
  gives_xp: 8 hitpoints
  respawn_time: 5000
}

enemy dragon {
  name: "Green Dragon"
  description: "A fearsome dragon"
  icon: "🐉"
  location: wilderness
  health: 150
  max_hit: 25
  attack_speed: 5
  attack_level: 68
  strength_level: 68
  defence_level: 68
  requires_skill: attack 60
  drops: 1 dragon_bones 1.0
  drops: 1 green_dragonhide 1.0
  drops: 1 dragon_spear 0.01
  gives_xp: 250 attack
  gives_xp: 83 hitpoints
  respawn_time: 30000
}
```

## Combat Mechanics

1. **Starting Combat**: Click "Attack" on an enemy
2. **Turn-Based**: Both player and enemy attack based on attack_speed
3. **Damage**: Calculated from strength and equipment bonuses
4. **Death**: If player dies, combat ends (no penalty)
5. **Victory**: Enemy drops loot, grants XP, and respawns after timer

## Combat Skills

Define combat-related skills:

```tfs
skill attack {
  name: "Attack"
  icon: "⚔️"
  max_level: 99
}

skill strength {
  name: "Strength"
  icon: "💪"
  max_level: 99
}

skill defence {
  name: "Defence"
  icon: "🛡️"
  max_level: 99
}

skill hitpoints {
  name: "Hitpoints"
  icon: "❤️"
  max_level: 99
}
```

## Display

Combat tab shows:
- Available enemies at current location
- Current combat status (health bars)
- Attack/flee buttons
- XP gained per kill
