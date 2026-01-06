---
type: docs
title: Platform Features
weight: 4
---

# Platform Features

Overview of the TickForge web platform capabilities.

## Playing Games

### Drag and Drop

1. Visit [tickforge.io](https://tickforge.io)
2. Drag a `.tfs` file onto the drop zone
3. Game loads and starts automatically

### File Browser

1. Click the drop zone
2. Select a `.tfs` file from your computer
3. Game loads and starts

### Example Games

Click example buttons on the landing page to try pre-built games:
- **Cookie Clicker** - Classic incremental game

## Save System

### Exporting Saves

1. While playing, click **Save** in the header
2. Save data is copied to clipboard (base64 encoded)
3. Paste and store somewhere safe

### Importing Saves

1. Click **Load** in the header
2. Paste your save data
3. Click "Load Save"
4. Game state restores

### Save Data Format

Saves are base64-encoded JSON containing:
- Resource amounts
- Generator counts
- Purchased upgrades
- Unlocked achievements
- Player level/XP
- Skill levels (for RPG games)
- Inventory contents
- Equipment
- Current location

## Game Info

If a game defines author/description/links:
1. An **i** button appears in the header
2. Click to view game info modal
3. Links open in new tabs

## Themes

Games can specify visual themes - we will make these suck less over time :)

- `default` - tickforge default
- `cookie` - Warm browns
- `dark-souls` - Dark with embers
- `retro-green` - Terminal style
- `neon-cyber` - Cyberpunk
- `fantasy` - Medieval RPG

## Navigation

### Header

- **Back arrow** - Return to landing page
- **Game title** - Current game name
- **Info button** - Game details (if available)
- **Save/Load** - Export/import progress
- **Bank** - Item storage (if available)
- **Level display** - Player progress

### Tabs (RPG Games)

RPG-style games show tabs:
- **Game** - Main idle mechanics
- **Skills** - Skill levels and XP
- **Inventory** - Item management
- **Map** - World navigation
- **Combat** - Fighting enemies
- **Crafting** - Recipe crafting

## Technical Details

### Data Storage

- No server-side storage
- All data is client-side
- Use Save/Load for persistence

### Performance

- Games run at a configurable discrete tick rate
- UI updates on each tick
- Optimized for thousands of generators

## Limitations

- Single game at a time
- No cloud saves
- No multiplayer
- No achievements sync
- No game discovery/sharing (yet)