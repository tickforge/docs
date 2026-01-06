---
type: docs
title: Bank
---

# Bank

The bank provides additional storage for items beyond inventory.

## Syntax

```tfs
bank {
  slots: 800
}
```

## Properties

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `slots` | number | `800` | Maximum unique item types |

## Usage

1. Click the **Bank** button in the game header
2. Bank modal shows:
   - Stored items (click to select, then withdraw)
   - Inventory items available to deposit

## Deposit

- Click an inventory item in the bank modal
- Choose "Deposit 1" or "Deposit All"

## Withdraw

- Click a bank item to select it
- Click "Take 1" or "Take All"
- Items go to inventory (requires free slots)

## Example

```tfs
inventory {
  slots: 28
}

bank {
  slots: 400
}

# Items that can be stored
item gold_ore {
  name: "Gold Ore"
  icon: "🪨"
  stackable: 1
}

item gold_bar {
  name: "Gold Bar"
  icon: "🟡"
  stackable: 1
}
```

## Notes

- Bank items stack regardless of item's `stackable` property
- Each unique item type uses one bank "slot"
- Bank is shared across all items (no tabs)
- Bank button only appears if `bank` is defined

## Differences from Inventory

| Feature | Inventory | Bank |
|---------|-----------|------|
| Access | Always available | Modal popup |
| Stacking | Per-item setting | Always stacks |
| Slots | Limited | Large capacity |
| Equipment | Can equip from | Cannot equip from |
| Crafting | Uses inventory | Cannot use bank |
