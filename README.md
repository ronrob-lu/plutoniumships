# Plutonium's Ships

Turn your static constructions into dynamic, pilotable boats or blimps and set off on the adventure aboard the ship of your dreams!

Plutonium's Ships is a powerful and versatile Minetest mod that breathes life into your creations. With just a helm, you can explore the world, transport your friends, and dominate the seas or skies in vessels that you design yourself.

## Features & Highlights

- **Complete Creative Freedom**: Build your ship however you like using a wide range of blocks. If you can build it, you can pilot it!
- **Sea & Sky**: Create majestic sailing ships, steampunk airships, or speedy modern boats.
- **Simple Controls**: Place a helm, board your creation, and steer it through the world with ease.
- **Dynamic Physics & Entities**: The mod transforms your block-based structures into moving entities, allowing smooth travel across the map.

## Technical Aspects

Plutonium's Ships achieves its magic by utilizing a robust structure-detection algorithm.

### How it Works
1. **Structure Detection**: When you activate the helm, the mod uses a flood-fill algorithm starting from the helm to identify all connected, allowed blocks within a specific radius.
2. **Entity Conversion**: Once the structure is mapped, the mod removes the blocks from the world and spawns a single, combined moving entity (or a set of entities) that perfectly replicates your ship's appearance.
3. **Movement & Physics**: The player's inputs at the helm are translated into movement vectors for the ship entity, providing intuitive control over speed, heading, and altitude (for blimps).
4. **Re-anchoring**: Upon exiting the helm or choosing to anchor, the entity is converted back into stationary blocks perfectly aligned with the world grid.

### Allowed Blocks
The mod maintains an internal list of allowed nodes (`ALLOWED_NODES` in `init.lua`) that can be safely merged into a ship structure. This list includes common building materials from `default`, such as wood, stone, glass, steel, and specific decor elements.

**Extending Allowed Blocks:**
If you wish to allow more blocks to be part of your ships, you can add them to the `ALLOWED_NODES` list in `init.lua`:
```lua
ALLOWED_NODES["your_mod:your_block"] = true
```

### Dependencies
- `default`
- `wool`

**Optional Dependencies:**
- `xdecor`: The mod no longer strictly depends on `xdecor`. Some blocks from `xdecor` (like barrels and lightboxes) are still explicitly supported if the mod is present. The crafting recipe for the balloons has been updated to use `default:paper` instead of `xdecor:rope`.

## Installation

1. Download or clone this repository.
2. Place the `plutoniumships` folder into your Minetest `mods` directory.
3. Enable the mod in your world configuration. Ensure you also have `default` and `wool` enabled.

## How to Play

1. **Build Your Ship**: Construct your vessel using supported blocks (wood, glass, steel, etc.). Keep it within a reasonable size to avoid performance drops. For airships, incorporate balloons (crafted with wool and paper).
2. **Place the Helm**: Craft a Ship Helm and place it on your ship. The front of the helm dictates the front of the ship.
3. **Set Sail**: Right-click the helm to take control. Your ship will lift off the grid, and you can steer it using your standard movement keys.
4. **Anchor**: When you reach your destination, right-click the helm again to anchor the ship, converting it back into regular blocks.

Set forth and conquer the blocky horizons!
