# Starry Valley - Architecture & Development Guide

## 📁 Project Structure

```
/game
├── dist/
│   └── starry-valley-ch2.html      # DEPLOYED GAME (built, tested, stable)
├── src/
│   └── (source code - to be extracted)
├── build/
│   └── (build scripts - for future use)
├── docs/
│   ├── GAMEPLAY.md                 # Player guide
│   ├── CONTRIBUTING.md             # How to contribute
│   ├── ARCHITECTURE.md             # This file
│   ├── DEVELOPMENT.md              # Development workflow
│   └── CHANGELOG.md                # Version history
├── .github/
│   ├── ISSUE_TEMPLATE/             # GitHub issue templates
│   └── pull_request_template.md    # PR template
├── README.md                        # Project overview
├── QUICKSTART.md                   # Quick setup guide
├── CLAUDE.md                        # Code documentation
└── starry-valley-ch2.html          # SOURCE GAME (working copy)
```

## 🎮 Game Architecture

### Current Implementation
- **Single-file HTML5 game** (~85KB)
- Pure JavaScript (no frameworks)
- Canvas 2D rendering
- Browser local storage for saves

### Key Systems

#### 1. Game State (Global G Object)
```javascript
const G = {
  phase: 'title|play|boss|dialog|menu|over',
  level: 1-3,
  tick: frame counter,
  hp: player health,
  gems: collected gems,
  P: player object,
  boss: boss object,
  projectiles: [],
  particles: [],
  // ... more properties
}
```

#### 2. Game Loop
```
Main Loop (60 FPS) {
  update()     // Update game logic
    ├── player movement
    ├── boss logic
    ├── collision detection
    ├── particle updates
    └── camera tracking
  
  render()     // Draw everything
    ├── background
    ├── tiles & objects
    ├── characters
    ├── UI
    └── effects
}
```

#### 3. Level Structure
Each level contains:
- Map layout (width, height, tile colors)
- Objects (gems, obstacles, interactive items)
- NPCs (characters with dialog)
- Boss configuration
- Story/narrative elements

#### 4. Boss System
Each boss has:
- Health and phases (1-3)
- Attack patterns (projectiles, area effects)
- Movement behavior
- Dialog/cutscenes
- Unique mechanics (to be implemented)

## 🔄 Development Workflow

### For Adding Features
1. **Never edit starry-valley-ch2.html directly for untested features**
2. Create a feature branch: `git checkout -b feature/your-feature`
3. Make changes incrementally
4. Test thoroughly in browser (F12 console for errors)
5. Keep commits small and focused
6. Create pull request with test results
7. Merge to main only after verified working

### Safe Development Practice
- Always keep `/dist/` with the last known **working** version
- Use feature branches for new features
- Test before committing
- Keep git history clean
- Document changes

## 🐛 Testing Checklist

Before considering a feature complete:
- [ ] No console errors (F12 → Console)
- [ ] Game loads without crashing
- [ ] Core gameplay works (movement, interaction)
- [ ] New feature works as intended
- [ ] Existing features still work
- [ ] No performance regression
- [ ] Tested on Chrome and Firefox

## 📝 Code Organization

### Current (Single File)
Lines are organized by function:
- CSS: 1-103
- HTML: 104-195
- JavaScript: 196-1814
  - Constants & state: 157-195
  - Level definitions: 200-500
  - Drawing functions: 505-850
  - Collision & physics: 829-1000
  - Boss logic: 1028-1220
  - Player logic: 1223-1500
  - Game loop: 1640-1800

### Future (Modular)
When codebase gets large, plan to split into:
- `src/constants.js` - Game constants
- `src/state.js` - Game state management
- `src/levels.js` - Level definitions
- `src/rendering.js` - All drawing code
- `src/input.js` - Keyboard/interaction
- `src/physics.js` - Collision & movement
- `src/bosses.js` - Boss logic
- `src/player.js` - Player logic
- `src/game.js` - Main loop

## 🎯 Current Status

### ✅ Working Features
- Player movement (WASD/arrows)
- NPC interaction with dialog
- Gem collection
- Crystal staff (rate-limited projectiles)
- Shield blocking (costs gems)
- 3 boss fights with phases
- HUD/UI system
- Save/load system
- Particle effects
- Camera following
- Level progression

### ⏳ In Development
- Boss unique mechanics (shockwaves, puddles, etc)
- Additional animations
- Environmental variety

### 📋 Known Issues
- Boss mechanics development needs careful testing
- Single-file architecture limits scalability

## 🚀 Next Steps

1. **Extract game code to modular structure** when single file gets too large
2. **Create proper level editor** for non-programmers
3. **Add asset pipeline** (sprites, sounds, music)
4. **Implement CI/CD** for automated testing
5. **Optimize performance** as features grow

---

**For questions, see CONTRIBUTING.md or CLAUDE.md**
