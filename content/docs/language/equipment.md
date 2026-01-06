---
type: docs
title: Equipment
---

# Equipment

Equipment items provide stat bonuses when worn.

## Syntax

```tfs
equipment identifier {
  name: "Display Name"
  icon: "X"
  description: "Description"
  slot: slot_type
  requires_skill: skill level
  attack_bonus: number
  strength_bonus: number
  defence_bonus: number
}
```

## Properties

| Property | Type | Required | Default | Description |
|----------|------|----------|---------|-------------|
| `name` | string | Yes | - | Display name |
| `icon` | string | Yes | - | Icon/emoji |
| `description` | string | No | - | Description |
| `slot` | slot type | Yes | - | Equipment slot |
| `requires_skill` | skill level | No | - | Skill requirement |
| `attack_bonus` | number | No | `0` | Attack accuracy bonus |
| `strength_bonus` | number | No | `0` | Damage bonus |
| `defence_bonus` | number | No | `0` | Defense bonus |

## Equipment Slots

| Slot | Description |
|------|-------------|
| `head` | Helmets, hats |
| `cape` | Capes, cloaks |
| `neck` | Necklaces, amulets |
| `weapon` | Swords, axes, bows |
| `body` | Chestplates, robes |
| `shield` | Shields, defenders |
| `legs` | Platelegs, robes |
| `hands` | Gloves, gauntlets |
| `feet` | Boots |
| `ring` | Rings |
| `ammo` | Arrows, bolts |

## Examples

### Weapons

```tfs
equipment bronze_sword {
  name: "Bronze Sword"
  icon: "🗡️"
  description: "A basic bronze sword"
  slot: weapon
  requires_skill: attack 1
  attack_bonus: 4
  strength_bonus: 3
  defence_bonus: 0
}

equipment iron_sword {
  name: "Iron Sword"
  icon: "🗡️"
  description: "A sturdy iron sword"
  slot: weapon
  requires_skill: attack 10
  attack_bonus: 10
  strength_bonus: 8
  defence_bonus: 0
}

equipment rune_scimitar {
  name: "Rune Scimitar"
  icon: "⚔️"
  description: "A powerful rune blade"
  slot: weapon
  requires_skill: attack 40
  attack_bonus: 45
  strength_bonus: 44
  defence_bonus: 0
}
```

### Armor

```tfs
equipment bronze_helm {
  name: "Bronze Helm"
  icon: "🪖"
  slot: head
  requires_skill: defence 1
  defence_bonus: 3
}

equipment iron_platebody {
  name: "Iron Platebody"
  icon: "🛡️"
  slot: body
  requires_skill: defence 10
  defence_bonus: 20
}

equipment rune_platelegs {
  name: "Rune Platelegs"
  icon: "🦵"
  slot: legs
  requires_skill: defence 40
  defence_bonus: 51
}
```

### Accessories

```tfs
equipment amulet_of_power {
  name: "Amulet of Power"
  icon: "📿"
  slot: neck
  attack_bonus: 6
  strength_bonus: 6
  defence_bonus: 6
}

equipment ring_of_wealth {
  name: "Ring of Wealth"
  icon: "💍"
  description: "Increases luck"
  slot: ring
}
```

## Obtaining Equipment

Equipment must be defined both as an `item` and `equipment`:

```tfs
# Define the item
item bronze_sword {
  name: "Bronze Sword"
  icon: "🗡️"
  stackable: 0
  value: 50
}

# Define equipment stats
equipment bronze_sword {
  name: "Bronze Sword"
  icon: "🗡️"
  slot: weapon
  attack_bonus: 4
  strength_bonus: 3
}
```

Equipment can be obtained via:
- Crafting recipes
- Enemy drops
- Purchased from shops (future feature)

## Display

Equipment panel shows:
- Equipment slots grid
- Currently equipped items
- Click to equip/unequip from inventory
