---
type: docs
title: Getting Started
weight: 1
---

# Getting Started

Create your first TickForge game in 5 minutes.

## Running Your First Game

1. Visit [tickforge.io](https://tickforge.io)
2. Click **Open Editor**
3. You'll see a starter template - click anywhere in the preview to start playing
4. Edit the code on the left to customize your game

## Understanding the Basics

Every TickForge game needs these core elements:

### 1. Game Declaration

```tfs
game "My Game" {
  version: "1.0"
  tick_rate: 1000
}
```

- `tick_rate` is in milliseconds (1000 = 1 second between ticks)

### 2. Resources

Resources are things players accumulate:

```tfs
resource coins {
  name: "Coins"
  icon: "$"
  initial: 0
}
```

### 3. Actions

Actions are buttons players click:

```tfs
action click {
  name: "Earn Coin"
  produces: 1 coins
  grants_xp: 1
}
```

### 4. Generators

Generators automatically produce resources each tick:

```tfs
generator worker {
  name: "Worker"
  description: "Earns coins automatically"
  cost: 10 coins
  cost_multiplier: 1.15
  produces: 1 coins
  requires: level 1
}
```

## Your First Complete Game

```tfs
game "Coin Collector" {
  version: "1.0"
  tick_rate: 1000
  author: "Your Name"
  description: "Collect coins and build your empire!"
  theme: "default"
}

resource coins {
  name: "Coins"
  icon: "$"
  initial: 0
}

player {
  xp_per_level: 100
}

action click {
  name: "Collect Coin"
  produces: 1 coins
  grants_xp: 1
}

generator worker {
  name: "Worker"
  description: "Collects 1 coin per second"
  cost: 10 coins
  cost_multiplier: 1.15
  produces: 1 coins
  requires: level 1
}

upgrade better_clicking {
  name: "Better Clicking"
  description: "Clicking gives +1 coin"
  cost: 50 coins
  effect: add click 1
}

achievement first_coin {
  name: "First Coin"
  description: "Collect your first coin"
  requires: 1 coins
  grants_xp: 10
}

achievement hundred_coins {
  name: "Coin Hoarder"
  description: "Collect 100 coins"
  requires: 100 coins
  grants_xp: 50
}
```

## Saving Your Game

1. In the editor, copy all your code
2. Save it to a `.tfs` file on your computer
3. Drag and drop the file onto tickforge.io to play anytime

## Next Steps

- [Language Reference](language/index.md) - Learn all available features
- [Editor Guide](editor.md) - Master the built-in editor
- [Themes](language/themes.md) - Customize your game's look
