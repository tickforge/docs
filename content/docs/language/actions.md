---
type: docs
title: Actions
---

# Actions

Actions are clickable buttons that produce resources when clicked.

## Syntax

```tfs
action identifier {
  name: "Display Name"
  produces: amount resource
  grants_xp: number
}
```

## Properties

| Property | Type | Required | Default | Description |
|----------|------|----------|---------|-------------|
| `name` | string | Yes | - | Button label |
| `produces` | amount | Yes | - | Resources gained per click |
| `grants_xp` | number | No | `0` | XP gained per click |

## Examples

### Basic Action

```tfs
action click {
  name: "Click!"
  produces: 1 gold
}
```

### Action with XP

```tfs
action mine {
  name: "Mine Gold"
  produces: 1 gold
  grants_xp: 1
}
```

### Multiple Actions

```tfs
action mine_gold {
  name: "Mine Gold"
  produces: 1 gold
  grants_xp: 1
}

action chop_wood {
  name: "Chop Wood"
  produces: 1 wood
  grants_xp: 1
}

action fish {
  name: "Fish"
  produces: 1 fish
  grants_xp: 2
}
```

## Upgrading Actions

Use upgrades to increase action output:

```tfs
action click {
  name: "Click"
  produces: 1 gold
}

upgrade better_click {
  name: "Better Clicking"
  description: "+1 gold per click"
  cost: 50 gold
  effect: add click 1  # Now produces 2 gold
}

upgrade super_click {
  name: "Super Clicking"
  description: "+5 gold per click"
  cost: 500 gold
  effect: add click 5  # Now produces 7 gold
}
```

## Display

Actions appear in the left panel of the game view as large, clickable buttons.
