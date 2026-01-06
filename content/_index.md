---
title: TickForge Documentation
---

# TickForge

A domain-specific language for incremental/idle games.

## What is TickForge?

TickForge is a scripting language that compiles to a browser-based game runtime. Write declarative game logic in `.tfs` files, drag-and-drop onto the web player, and your game runs instantly. No build step, no dependencies, no framework churn.

The language handles the boring parts - resource management, cost scaling, save/load, UI rendering - so you can focus on game design.

```tfs
game "My Game" {
  version: "1.0"
  tick_rate: 1000
}

resource gold {
  name: "Gold"
  icon: "$"
  initial: 0
}

generator miner {
  name: "Miner"
  cost: 10 gold
  cost_multiplier: 1.15
  produces: 1 gold
}
```

## Why?

Incremental games are the perfect "small but complete" game genre. They're simple enough to finish, complex enough to be interesting, and endlessly tweakable. But building one from scratch means reinventing the same systems every time: tick loops, exponential costs, prestige layers, save serialization.

TickForge extracts the common patterns into a language. You describe *what* your game does, not *how* to render buttons or calculate compound interest.

## Goals

**Short term:** A complete, documented DSL that covers 80% of incremental game mechanics. Cookie Clicker to Melvor Idle complexity.

**Long term:** A platform where anyone can create, share, and play incremental games without touching JavaScript. Think "Scratch for idle games" but without the toy aesthetic.

## Roadmap

- [x] Core engine (resources, generators, upgrades, achievements)
- [x] RPG systems (skills, inventory, combat, crafting)
- [x] Browser-based editor with live preview
- [x] Theming system
- [x] Save/load export
- [ ] Prestige/ascension mechanics
- [ ] Conditional logic and events
- [ ] Asset imports (custom icons, sounds)
- [ ] Game sharing & discovery
- [ ] Offline progress calculation
- [ ] Mobile-responsive UI

## Documentation

- [Getting Started](/docs/getting-started/) - Build your first game in 5 minutes
- [Language Reference](/docs/language/) - Complete syntax documentation
- [Editor Guide](/docs/editor/) - Using the built-in editor
- [Platform Features](/docs/platform/) - Web runtime capabilities

## Support

TickForge is free and open source. If you want to support development:

- [Patreon](https://patreon.com/c/tickforge) - Monthly support
- [Discord](https://discord.gg/KNPV4XcYKW) - Community & feedback
- [GitHub](https://github.com/tickforge/issues) - Issues & discussion

## Status

Early but usable. The core language is in preview. Breaking changes are possible but will be documented. Expect rough edges.