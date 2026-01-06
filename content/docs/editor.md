---
type: docs
title: Editor Guide
weight: 3
---

# Editor Guide

The built-in TickForge editor provides a complete development environment.

## Opening the Editor

1. Visit [tickforge.io](https://tickforge.io)
2. Click **Open Editor**

## Interface

```
┌─────────────────────────────────────────────────────────┐
│  [Back]  TickForge Editor          [ ] Auto-compile    │
├────────────────────────┬────────────────────────────────┤
│  game.tfs              │  Preview            [Restart] │
├────────────────────────┼────────────────────────────────┤
│  1│ # My Game          │                                │
│  2│ game "My Game" {   │    ┌──────────────────────┐   │
│  3│   version: "1.0"   │    │                      │   │
│  4│ }                  │    │    Live Game         │   │
│  5│                    │    │    Preview           │   │
│  6│ resource gold {    │    │                      │   │
│  7│   name: "Gold"     │    └──────────────────────┘   │
│  8│   ...              │                                │
├────────────────────────┤                                │
│ ❌ Compilation Error   │                                │
│ Line 7: Expected '}'   │                                │
└────────────────────────┴────────────────────────────────┘
```

## Features

### Live Preview

The right panel shows your game running in real-time. Changes compile automatically after 500ms of inactivity.

### Auto-Compile

- **Enabled (default)**: Code compiles automatically as you type
- **Disabled**: Click "Compile" button to manually compile

### Line Numbers

Line numbers help identify error locations. Scroll syncs between code and line numbers.

### Tab Support

Press Tab to insert 2 spaces (standard indentation).

### Error Panel

Compilation errors appear below the editor with:
- Error icon
- Error message
- Often includes line number

### Restart Button

Click "Restart" in the preview header to reset the game state while keeping your code.

## Keyboard Shortcuts

| Key | Action |
|-----|--------|
| Tab | Insert 2 spaces |
| Ctrl/Cmd + A | Select all |
| Ctrl/Cmd + C | Copy |
| Ctrl/Cmd + V | Paste |
| Ctrl/Cmd + Z | Undo |

## Workflow

### Starting Fresh

1. Open editor (loads starter template)
2. Modify the template or clear and start fresh
3. Preview updates automatically

### Editing Existing Game

1. Open your `.tfs` file in a text editor
2. Copy the contents
3. Open TickForge editor
4. Select all and paste your code

### Saving Your Work

The editor doesn't save automatically. To save:

1. Select all code (Ctrl/Cmd + A)
2. Copy (Ctrl/Cmd + C)
3. Paste into a text editor
4. Save as `yourname.tfs`

### Testing Changes

1. Make edits in the code panel
2. Wait for auto-compile (or click Compile)
3. Test in preview panel
4. Click Restart to reset game state

## Tips

### Debugging

- Check the error panel for syntax errors
- Errors often include line numbers
- Common issues:
  - Missing closing braces `}`
  - Missing colons after properties
  - Typos in identifiers

### Performance

- Large games may take longer to compile
- Disable auto-compile for complex edits
- Use Restart instead of recompiling for state reset

### Organization

```tfs
# Use comments to organize sections
# ============================================
# RESOURCES
# ============================================

resource gold { ... }
resource gems { ... }

# ============================================
# GENERATORS
# ============================================

generator miner { ... }
```

## Limitations

- No syntax highlighting (yet)
- No autocomplete (yet)
- No file management (copy/paste to save)
- No multi-file support

## External Editors

For larger projects, consider using an external editor:

- **VS Code** - Install a custom language extension
- **Sublime Text** - Use generic syntax highlighting
- **Any text editor** - `.tfs` files are plain text

Then drag-and-drop the file onto tickforge.io to play.
