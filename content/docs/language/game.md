---
type: docs
title: Game Declaration
---

# Game Declaration

The `game` block defines metadata and settings for your game.

## Syntax

```tfs
game "Game Name" {
  version: "1.0"
  tick_rate: 1000
  author: "Your Name"
  description: "A description of your game"
  theme: "default"
  link: "Label" "https://example.com"
}
```

## Properties

| Property | Type | Required | Default | Description |
|----------|------|----------|---------|-------------|
| `version` | string | No | `"1.0"` | Game version number |
| `tick_rate` | number | No | `1000` | Milliseconds between game ticks |
| `author` | string | No | - | Game creator's name |
| `description` | string | No | - | Game description |
| `theme` | string | No | `"default"` | Visual theme name |
| `link` | string string | No | - | External link (can have multiple) |

## Tick Rate

The `tick_rate` controls how often generators produce resources:

- `1000` = 1 tick per second (default)
- `500` = 2 ticks per second
- `2000` = 1 tick every 2 seconds

```tfs
game "Fast Game" {
  tick_rate: 500  # Twice as fast
}
```

## Links

Add multiple links to your game:

```tfs
game "My Game" {
  link: "Discord" "https://discord.gg/..."
  link: "GitHub" "https://github.com/..."
  link: "Donate" "https://ko-fi.com/..."
}
```

Links appear in the game info modal (click the "i" button in the header).

## Themes

See [Themes](themes.md) for available theme options.

## Example

```tfs
game "Cookie Clicker" {
  version: "2.0"
  tick_rate: 1000
  author: "TickForge Demo"
  description: "Bake cookies and build your empire!"
  theme: "cookie"
  link: "Discord" "https://discord.gg/KNPV4XcYKW"
  link: "Docs" "http://docs.tickforge.io/"
}
```
