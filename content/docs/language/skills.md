---
type: docs
title: Skills
---

# Skills

Skills provide an RPG-style progression system separate from the main player level.

## Syntax

```tfs
skill identifier {
  name: "Display Name"
  icon: "X"
  max_level: 99
}
```

## Properties

| Property | Type | Required | Default | Description |
|----------|------|----------|---------|-------------|
| `name` | string | Yes | - | Skill display name |
| `icon` | string | Yes | - | Icon/emoji for the skill |
| `max_level` | number | No | `99` | Maximum skill level |

## Gaining Skill XP

Skills gain XP through nodes and recipes:

### From Nodes

```tfs
node oak_tree {
  name: "Oak Tree"
  location: forest
  gives: 1 oak_log
  gives_xp: 25 woodcutting  # Grants woodcutting XP
  cooldown: 3000
}
```

### From Recipes

```tfs
recipe bronze_bar {
  name: "Bronze Bar"
  consumes: 1 copper_ore, 1 tin_ore
  produces: 1 bronze_bar
  gives_xp: 15 smithing  # Grants smithing XP
}
```

## Skill Requirements

Use skills as requirements for content:

### Node Requirements

```tfs
node magic_tree {
  name: "Magic Tree"
  location: forest
  requires_skill: woodcutting 75
  gives: 1 magic_log
  gives_xp: 250 woodcutting
}
```

### Recipe Requirements

```tfs
recipe rune_sword {
  name: "Rune Sword"
  requires_skill: smithing 50
  consumes: 2 rune_bar
  produces: 1 rune_sword
  gives_xp: 75 smithing
}
```

### Equipment Requirements

```tfs
equipment rune_pickaxe {
  name: "Rune Pickaxe"
  slot: weapon
  requires_skill: mining 40
  attack_bonus: 0
  strength_bonus: 0
}
```

## XP Formula

Skill XP required per level is as follows:

```
XP for level N ≈ (N^2 + N) / 2 * 50
```

Approximate XP totals:
- Level 10: ~2,750 XP
- Level 50: ~63,750 XP
- Level 99: ~245,000 XP

## Example: RuneScape-Style Skills

```tfs
skill mining {
  name: "Mining"
  icon: "⛏️"
  max_level: 99
}

skill smithing {
  name: "Smithing"
  icon: "🔨"
  max_level: 99
}

skill woodcutting {
  name: "Woodcutting"
  icon: "🪓"
  max_level: 99
}

skill fishing {
  name: "Fishing"
  icon: "🎣"
  max_level: 99
}

skill cooking {
  name: "Cooking"
  icon: "🍳"
  max_level: 99
}
```

## Display

Skills appear in the Skills tab showing:
- Skill icon and name
- Current level
- XP progress bar
- XP to next level
