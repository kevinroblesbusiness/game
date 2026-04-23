# Development Guide for Starry Valley

This document helps developers understand and modify the game code.

## 🔍 Project Overview

**Type**: Single-file HTML5 Game  
**Language**: HTML + CSS + JavaScript  
**Size**: ~86KB (includes everything)  
**Browser Support**: Modern browsers (Chrome, Firefox, Safari, Edge)

## 📋 File Structure

### `starry-valley-ch2.html`
The main (and only) game file containing:
- **CSS** (lines 1-103): Styling for UI and game elements
- **HTML** (lines 104-195): Game containers and UI elements
- **JavaScript** (lines 196-1814): All game logic

## 🏗️ Code Organization

### Global Constants (line 157)
```javascript
const T = 32;  // Tile size in pixels
```

### Game State Object (line ~159-180)
```javascript
const G = {
  tick: 0,           // Current frame number
  level: 1,          // Current level (1-3)
  phase: 'play',     // Game phase: 'title', 'play', 'boss', 'dialog', 'menu'
  P: {},            // Player object
  cam: {},          // Camera position
  objs: [],         // Objects in level (gems, items)
  npcs: [],         // NPCs in level
  boss: null,       // Boss object (if level has boss)
  // ... more properties
}
```

### Key Functions

| Function | Purpose | Line |
|----------|---------|------|
| `loadLevel(n)` | Load a game level | 1398 |
| `update()` | Update game state each frame | 1640 |
| `render()` | Draw everything to canvas | 1687 |
| `loop()` | Main game loop (60 FPS) | 1766 |
| `drawAngie()` | Draw player character | 505 |
| `drawNPC()` | Draw NPC characters | 575 |
| `drawBoss()` | Draw boss enemy | 600 |
| `drawTile()` | Draw map tiles/objects | 753 |

### Level Definition (line 200+)
Each level has:
```javascript
{
  name: "Level Name",
  size: { w: 36, h: 22 },        // Map dimensions in tiles
  bg: "#color",                  // Tile background color
  bgAlt: "#color",               // Alternate tile color
  objs: [{t: "gem", x: 5, y: 3}], // Objects to place
  npcs: [{name: "NPC", x: 10, y: 5}], // NPCs to place
  // ... more properties
}
```

## 🎨 Main Game Loop

```
1. loadLevel() → Initialize level
2. loop() runs every ~16ms (60 FPS):
   └─ update() → Update game logic
      └─ update player position
      └─ update camera
      └─ update animations
   └─ render() → Draw everything
      └─ fill background
      └─ draw tiles
      └─ draw objects/NPCs
      └─ draw UI
```

## 🐛 Recent Fixes

### Map Tile Rendering (Apr 23, 2026)
**Issue**: Map tiles weren't aligning properly with screen  
**Cause**: Camera translation used floored coordinates while tile culling used fractional values  
**Fix**: Changed `ctx.translate(-Math.floor(G.cam.x), ...)` to `ctx.translate(-G.cam.x, ...)`  
**Line**: 1704

## 💡 Common Tasks

### Adding a New Level
1. Add new object to `LEVELS` array (around line 200)
2. Define `name`, `size`, `bg`, `bgAlt` properties
3. Add `objs` array for items and obstacles
4. Add `npcs` array for characters
5. Add story/dialog data

### Modifying Player Movement
- Player speed: See `G.P.speed` (updated in `update()`)
- Animation frames: `drawAngie()` function (line 505)
- Collision detection: Search for "collision" or "blocked"

### Changing Colors
- UI colors: CSS section (lines 1-103)
- Tile colors: Level `bg` and `bgAlt` properties
- Character colors: In `drawAngie()`, `drawNPC()` functions

## 🔧 Development Workflow

1. **Edit the file**: Open `starry-valley-ch2.html` in your editor
2. **Test**: Refresh browser to see changes
3. **Commit**: `git add starry-valley-ch2.html && git commit -m "Description"`
4. **Push**: `git push -u origin your-branch-name`

## 📚 Resources

- **Canvas API**: https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API
- **JavaScript**: https://developer.mozilla.org/en-US/docs/Web/JavaScript
- **Git Guide**: https://guides.github.com/

## 🎯 Next Steps for Developers

1. Read through the `update()` and `render()` functions to understand game flow
2. Look at `drawAngie()` to see how sprites are drawn
3. Check `LEVELS` array to see how levels are structured
4. Try making small changes and testing them in the browser

---

**Questions?** Check the code comments or look at similar functions for reference!
