---
type: docs
title: Generators
---

# Generators

Generators automatically produce resources each game tick.

## Syntax

```tfs
generator identifier {
  name: "Display Name"
  description: "Description text"
  cost: amount resource
  cost_multiplier: number
  produces: amount resource
  requires: requirement
}
```

## Properties

| Property | Type | Required | Default | Description |
|----------|------|----------|---------|-------------|
| `name` | string | Yes | - | Display name |
| `description` | string | No | - | Description shown in UI |
| `cost` | amount | Yes | - | Base purchase cost |
| `cost_multiplier` | number | No | `1.15` | Cost increase per purchase |
| `produces` | amount | Yes | - | Resources produced per tick |
| `requires` | requirement | No | - | Unlock requirement |

## Cost Scaling

Each generator purchased increases the cost:

```
cost = base_cost * (cost_multiplier ^ owned_count)
```

With `cost: 10 gold` and `cost_multiplier: 1.15`:
- 1st: 10 gold
- 2nd: 11.5 gold
- 3rd: 13.2 gold
- 10th: 40.5 gold

## Requirements

### Level Requirement

```tfs
generator advanced {
  name: "Advanced Generator"
  cost: 1000 gold
  produces: 10 gold
  requires: level 5
}
```

### Count Requirement

```tfs
generator super_miner {
  name: "Super Miner"
  cost: 10000 gold
  produces: 100 gold
  requires: 10 miner  # Need 10 miners first
}
```

## Examples

### Cookie Clicker Style

```tfs
generator cursor {
  name: "Cursor"
  description: "Auto-clicks once per 10 seconds"
  cost: 15 cookies
  cost_multiplier: 1.15
  produces: 0.1 cookies
}

generator grandma {
  name: "Grandma"
  description: "Bakes cookies for you"
  cost: 100 cookies
  cost_multiplier: 1.15
  produces: 1 cookies
  requires: level 2
}

generator farm {
  name: "Farm"
  description: "Grows cookie plants"
  cost: 1100 cookies
  cost_multiplier: 1.15
  produces: 8 cookies
  requires: level 3
}
```

## Upgrading Generators

Use upgrades to multiply generator output:

```tfs
upgrade efficient_miners {
  name: "Efficient Miners"
  description: "Miners produce 2x resources"
  cost: 500 gold
  requires: 5 miner
  effect: multiply miner 2
}
```

## Display

Generators appear in the middle panel showing:
- Name and description
- Current cost
- Number owned
- Production rate
- Buy button (disabled if requirements not met)
