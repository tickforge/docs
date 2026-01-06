---
type: docs
title: Endgame & Credits
---

# Endgame & Credits

Define win conditions and credits for your game.

## Endgame

The `endgame` block defines the win condition:

```tfs
endgame {
  requires: requirement
  message: "Congratulations message"
}
```

### Properties

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| `requires` | requirement | Yes | Win condition |
| `message` | string | Yes | Victory message |

### Examples

```tfs
# Win by accumulating resources
endgame {
  requires: 1000000000 cookies
  message: "You've baked a billion cookies! The Cookie Empire is complete!"
}

# Win by reaching a level
endgame {
  requires: level 100
  message: "You've reached the maximum level! You are a true master!"
}

# Win by owning generators
endgame {
  requires: 100 dragon
  message: "With 100 dragons, you rule the skies!"
}
```

## Credits

The `credits` block shows during the endgame scenario:

```tfs
credits {
  title: "Game Title"
  author: "Author Name"
  text: "Thank you message and credits"
}
```

### Properties

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| `title` | string | Yes | Game title |
| `author` | string | Yes | Creator name |
| `text` | string | Yes | Credits text (supports \n) |

### Example

```tfs
credits {
  title: "Cookie Clicker"
  author: "TickForge Demo"
  text: "Thanks for playing!\n\nThis game was created using TickForge,\na scripting language for incremental games.\n\nOriginal Cookie Clicker by Orteil.\n\nSpecial thanks to our Discord community!"
}
```

## Complete Example

```tfs
game "Space Empire" {
  version: "1.0"
  author: "Game Dev"
}

resource planets {
  name: "Planets"
  icon: "🪐"
  initial: 0
}

# ... game content ...

endgame {
  requires: 1000 planets
  message: "You've colonized 1000 planets! The galaxy is yours!"
}

credits {
  title: "Space Empire"
  author: "Game Dev"
  text: "Congratulations, Galactic Emperor!\n\nYou've conquered the stars.\n\nThank you for playing Space Empire.\n\nCreated with TickForge\nhttps://tickforge.io"
}
```

## Display

When the endgame condition is met:
1. Game pauses
2. Victory message displays
3. Credits screen overlay appears
4. Player can dismiss to continue playing (post-game)

## Notes

- Endgame is optional - games can be endless
- Credits are optional but recommended
- Use `\n` for line breaks in credits text
- Game continues after credits (player can keep playing)
