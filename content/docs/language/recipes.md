---
type: docs
title: Recipes
---

# Recipes

Recipes allow players to craft items from other items.

## Syntax

```tfs
recipe identifier {
  name: "Display Name"
  description: "Description"
  requires_skill: skill level
  consumes: quantity item, quantity item
  produces: quantity item
  gives_xp: amount skill
  ticks: number
}
```

## Properties

| Property | Type | Required | Default | Description |
|----------|------|----------|---------|-------------|
| `name` | string | Yes | - | Display name |
| `description` | string | No | - | Description |
| `requires_skill` | skill level | No | - | Skill requirement |
| `consumes` | item list | Yes | - | Input materials |
| `produces` | item list | Yes | - | Output items |
| `gives_xp` | amt skill | No | - | XP reward |
| `ticks` | number | No | `1` | Ticks to complete |

## Examples

### Basic Crafting

```tfs
recipe bronze_bar {
  name: "Bronze Bar"
  description: "Smelt copper and tin into bronze"
  requires_skill: smithing 1
  consumes: 1 copper_ore, 1 tin_ore
  produces: 1 bronze_bar
  gives_xp: 6 smithing
}
```

### Multiple Inputs

```tfs
recipe steel_bar {
  name: "Steel Bar"
  description: "Smelt iron with coal"
  requires_skill: smithing 30
  consumes: 1 iron_ore, 2 coal
  produces: 1 steel_bar
  gives_xp: 18 smithing
}
```

### Multiple Outputs

```tfs
recipe uncut_gem {
  name: "Cut Gem"
  description: "Cut a gem and keep the dust"
  requires_skill: crafting 20
  consumes: 1 uncut_ruby
  produces: 1 ruby, 1 gem_dust
  gives_xp: 25 crafting
}
```

### Cooking

```tfs
recipe cooked_shrimp {
  name: "Cooked Shrimp"
  description: "Cook raw shrimp"
  requires_skill: cooking 1
  consumes: 1 raw_shrimp
  produces: 1 cooked_shrimp
  gives_xp: 30 cooking
}

recipe cooked_lobster {
  name: "Cooked Lobster"
  description: "Cook raw lobster"
  requires_skill: cooking 40
  consumes: 1 raw_lobster
  produces: 1 cooked_lobster
  gives_xp: 120 cooking
}
```

### Smithing Equipment

```tfs
recipe bronze_sword {
  name: "Bronze Sword"
  description: "Forge a bronze sword"
  requires_skill: smithing 4
  consumes: 1 bronze_bar
  produces: 1 bronze_sword
  gives_xp: 12 smithing
}

recipe iron_platebody {
  name: "Iron Platebody"
  description: "Forge iron armor"
  requires_skill: smithing 33
  consumes: 5 iron_bar
  produces: 1 iron_platebody
  gives_xp: 125 smithing
}
```

## Timed Crafting

Use `ticks` for recipes that take time:

```tfs
recipe dragon_armor {
  name: "Dragon Armor"
  description: "A legendary piece of armor"
  requires_skill: smithing 90
  consumes: 10 dragon_bar, 1 dragon_scale
  produces: 1 dragon_platebody
  gives_xp: 500 smithing
  ticks: 10  # Takes 10 game ticks
}
```

## Display

Crafting tab shows:
- Available recipes (meeting skill requirements)
- Locked recipes (with requirement shown)
- Material requirements (colored by availability)
- Craft button (disabled if missing materials)
