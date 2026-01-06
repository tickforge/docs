---
type: docs
title: Themes
---

# Themes

TickForge includes 6 built-in themes to customize your game's visual style.

## Setting a Theme

```tfs
game "My Game" {
  theme: "cookie"
}
```

## Available Themes

### `default`
Classic Miniclip 2009 style with blue backgrounds and orange accents.
- Deep blue/slate backgrounds
- Cyan and orange highlights
- Clean, modern feel

### `cookie`
Warm, inviting theme perfect for cookie/baking games.
- Brown and amber tones
- Golden highlights
- Cozy atmosphere

### `dark-souls`
Grim, dark theme with ember accents.
- Near-black backgrounds
- Orange/red ember highlights
- Somber, serious mood

### `retro-green`
Classic terminal/matrix aesthetic.
- Pure black background
- Green phosphor text
- Nostalgic hacker vibe

### `neon-cyber`
Vibrant cyberpunk theme.
- Purple/violet backgrounds
- Fuchsia and cyan neon accents
- Futuristic feel

### `fantasy`
Medieval RPG theme.
- Deep indigo/purple backgrounds
- Gold and amber accents
- Magical atmosphere

## Theme Preview

| Theme | Background | Primary | Accent |
|-------|------------|---------|--------|
| default | Slate | Cyan | Orange |
| cookie | Amber/Brown | Amber | Yellow |
| dark-souls | Near Black | Orange | Red |
| retro-green | Black | Green | Lime |
| neon-cyber | Violet | Fuchsia | Cyan |
| fantasy | Indigo | Amber | Purple |

## Custom Colors (Advanced)

You can override specific theme colors:

```tfs
game "My Game" {
  theme: "default"
  primary_color: "#ff6b6b"
  secondary_color: "#1a1a2e"
  accent_color: "#ffd93d"
  bg_color: "#0f0f23"
}
```

Note: Custom colors are experimental and may not apply to all UI elements.

## Theme Recommendations

| Game Type | Recommended Theme |
|-----------|-------------------|
| Cookie/Baking | `cookie` |
| Mining/Resources | `default` |
| RPG/Adventure | `fantasy` |
| Sci-Fi | `neon-cyber` |
| Horror/Souls-like | `dark-souls` |
| Hacking/Tech | `retro-green` |
