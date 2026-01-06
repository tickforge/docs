---
type: docs
title: Resources
---

# Resources

Resources are values that players accumulate throughout the game.

## Syntax

```tfs
resource identifier {
  name: "Display Name"
  icon: "X"
  initial: 0
}
```

## Properties

| Property | Type | Required | Default | Description |
|----------|------|----------|---------|-------------|
| `name` | string | Yes | - | Display name shown in UI |
| `icon` | string | Yes | - | Icon/emoji shown with resource |
| `initial` | number | No | `0` | Starting amount |

## Examples

### Basic Resource

```tfs
resource gold {
  name: "Gold"
  icon: "$"
  initial: 0
}
```

### Multiple Resources

```tfs
resource coins {
  name: "Coins"
  icon: "$"
  initial: 100  # Start with 100 coins
}

resource gems {
  name: "Gems"
  icon: "*"
  initial: 0
}

resource wood {
  name: "Wood"
  icon: "#"
  initial: 0
}
```

### Using Emoji Icons

```tfs
resource cookies {
  name: "Cookies"
  icon: "🍪"
  initial: 0
}

resource gold {
  name: "Gold"
  icon: "🪙"
  initial: 0
}
```

## Usage

Resources are referenced by their identifier in other blocks:

```tfs
resource gold {
  name: "Gold"
  icon: "$"
  initial: 0
}

# Reference the resource by its identifier
action mine {
  produces: 1 gold
}

generator miner {
  cost: 10 gold
  produces: 1 gold
}
```

## Display

Resources appear in the resource bar at the top of the game screen, showing:
- Icon
- Name
- Current amount
- Production rate (per second)
