# Starry Valley - Chapter 2

A pixel-art adventure game where you play as Angie exploring Starry Valley to solve mysteries and collect clues.

## 🎮 How to Play

1. Open **`dist/starry-valley-ch2.html`** in your web browser (this is the stable, tested version)
2. Use **Arrow Keys** or **WASD** to move around
3. Press **T** or **Space** to talk to NPCs and interact
4. Collect **5 gems** per level and defeat the boss
5. Use number keys **1-4** to select tools:
   - **1**: Hand (collect gems, interact)
   - **2**: Shield (block attacks - costs 1 gem to charge)
   - **3**: Crystal Staff (shoot projectiles at boss)
   - **4**: Journal (view story and clues)

## 📁 Project Structure

```
game/
├── dist/                          # 🎮 PLAY THE GAME HERE
│   └── starry-valley-ch2.html     # ← Stable, tested release
├── src/                           # Source code (for future modularization)
├── build/                         # Build scripts (for future use)
├── docs/
│   ├── GAMEPLAY.md                # Player's guide
│   ├── CONTRIBUTING.md            # How to contribute
│   ├── ARCHITECTURE.md            # Code structure & design
│   ├── DEVELOPMENT.md             # Development workflow
│   └── CHANGELOG.md               # Version history
├── .github/
│   ├── ISSUE_TEMPLATE/
│   └── pull_request_template.md
├── README.md                      # This file
├── CLAUDE.md                      # Code documentation
├── QUICKSTART.md                  # Quick setup guide
└── starry-valley-ch2.html         # Working copy (source)
```

## 🚀 Getting Started

**Just want to play?**
```
Open: dist/starry-valley-ch2.html
```

**Want to develop/modify?**
1. Read [DEVELOPMENT.md](./docs/DEVELOPMENT.md) for workflow
2. Read [ARCHITECTURE.md](./docs/ARCHITECTURE.md) for code structure
3. See [CLAUDE.md](./CLAUDE.md) for code documentation

## ✅ Current Status

- ✨ 3 complete levels with full boss fights
- 🎮 Complete gameplay loop (exploration → collection → boss battle)
- 💾 Save/load system with browser storage
- 🎨 Animated environments and effects
- 📊 Health, gem, and objective tracking
- 🛡️ Shield and projectile combat system
- 📖 NPC dialogue and story progression

## 🐛 Reporting Issues

Found a bug? [Create an issue](../../issues/new)

Include:
- What happened
- Steps to reproduce
- What you expected to happen
- Browser and OS

## 🤝 Contributing

Want to improve the game? [Read CONTRIBUTING.md](./docs/CONTRIBUTING.md)

**Development workflow:**
1. Create feature branch from `main`
2. Make ONE small, focused change
3. Test thoroughly in browser
4. Commit with clear message
5. Push and create pull request

See [DEVELOPMENT.md](./docs/DEVELOPMENT.md) for detailed guide.

## 📚 Documentation

- **[GAMEPLAY.md](./docs/GAMEPLAY.md)** - Complete player guide
- **[DEVELOPMENT.md](./docs/DEVELOPMENT.md)** - How to develop features
- **[ARCHITECTURE.md](./docs/ARCHITECTURE.md)** - Code structure & design
- **[CONTRIBUTING.md](./docs/CONTRIBUTING.md)** - Contribution guidelines
- **[CHANGELOG.md](./docs/CHANGELOG.md)** - Version history
- **[CLAUDE.md](./CLAUDE.md)** - Code documentation

## 📈 Game Features

### Gameplay
- Exploration-based adventure
- NPC interaction with dialogue trees
- Gem collection system
- Boss battles with phases
- Inventory/tool system
- Health/damage system

### Technical
- Pure JavaScript (no frameworks)
- Canvas 2D rendering
- 60 FPS performance
- Local browser storage saves
- Responsive layout

## 🎯 Development Status

### ✅ Complete
- Core game loop
- 3 boss fights
- Level progression
- Save system
- UI/HUD

### ⏳ In Progress
- Boss unique mechanics
- Additional animations

### 📋 Planned
- Environmental variety
- More levels
- Modular code architecture
- Sound system

## 📞 Questions?

- Check the docs folder
- Read CLAUDE.md for code questions
- Create an issue for bugs

---

**Play:** `dist/starry-valley-ch2.html`  
**Last Updated:** April 23, 2026  
**Current Version:** 1.0.0 Stable

