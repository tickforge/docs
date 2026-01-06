---
type: docs
title: Locations & Nodes
---

# Locations & Nodes

Create a world map with gatherable resource nodes.

## Location Syntax

```tfs
location identifier {
  name: "Display Name"
  description: "Location description"
  icon: "X"
  connections: other_location, another_location
}
```

## Location Properties

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| `name` | string | Yes | Display name |
| `description` | string | No | Description text |
| `icon` | string | Yes | Icon/emoji |
| `connections` | id list | No | Connected locations |

## Node Syntax

```tfs
node identifier {
  name: "Display Name"
  description: "Node description"
  icon: "X"
  location: location_id
  requires_skill: skill level
  gives: quantity item
  gives_xp: amount skill
  cooldown: milliseconds
  depletion_chance: 0.0-1.0
}
```

## Node Properties

| Property | Type | Required | Default | Description |
|----------|------|----------|---------|-------------|
| `name` | string | Yes | - | Display name |
| `description` | string | No | - | Description text |
| `icon` | string | Yes | - | Icon/emoji |
| `location` | id | Yes | - | Where node appears |
| `requires_skill` | skill level | No | - | Skill requirement |
| `gives` | amount item | Yes | - | Item reward |
| `gives_xp` | amount skill | No | - | XP reward |
| `cooldown` | number | No | `3000` | Ms between harvests |
| `depletion_chance` | number | No | `0` | Chance to deplete (0-1) |

## Example World

```tfs
# Locations
location lumbridge {
  name: "Lumbridge"
  description: "A peaceful starting town"
  icon: "🏠"
  connections: forest, mine
}

location forest {
  name: "Forest"
  description: "Dense woodland"
  icon: "🌲"
  connections: lumbridge, swamp
}

location mine {
  name: "Mine"
  description: "Dark mining tunnels"
  icon: "⛏️"
  connections: lumbridge
}

# Nodes in Forest
node oak_tree {
  name: "Oak Tree"
  description: "A sturdy oak tree"
  icon: "🌳"
  location: forest
  requires_skill: woodcutting 1
  gives: 1 oak_log
  gives_xp: 25 woodcutting
  cooldown: 3000
}

node willow_tree {
  name: "Willow Tree"
  description: "A graceful willow"
  icon: "🌴"
  location: forest
  requires_skill: woodcutting 30
  gives: 1 willow_log
  gives_xp: 68 woodcutting
  cooldown: 4000
}

# Nodes in Mine
node copper_rock {
  name: "Copper Rock"
  description: "Contains copper ore"
  icon: "🪨"
  location: mine
  requires_skill: mining 1
  gives: 1 copper_ore
  gives_xp: 18 mining
  cooldown: 2500
}

node iron_rock {
  name: "Iron Rock"
  description: "Contains iron ore"
  icon: "ite"
  location: mine
  requires_skill: mining 15
  gives: 1 iron_ore
  gives_xp: 35 mining
  cooldown: 4000
}
```

## Navigation

Players navigate via the Map tab:
- Current location shown with nodes/enemies
- Connected locations shown as clickable buttons
- Travel is instant

## Display

- Map tab shows current location info
- Available nodes shown with gather buttons
- Cooldown displayed on recently used nodes
- Locked nodes shown if skill requirement not met
