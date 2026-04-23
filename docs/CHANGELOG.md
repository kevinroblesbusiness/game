# Changelog - Starry Valley Chapter 2

All notable changes to this project will be documented in this file.

## [Unreleased]
- Boss unique mechanics in development
- Environmental variety planned

## [1.0.0] - 2026-04-23 (Current Stable)

### ✅ Features
- **3 Complete Levels** with unique bosses and stories
- **Player Movement** (WASD/Arrow keys)
- **NPC Interaction** with branching dialog
- **Gem Collection** system (5 gems per level)
- **Combat System**
  - Crystal Staff: Rate-limited projectiles (1.5 stars/sec)
  - Shield: Blocks attacks (costs 1 gem, 2 second duration)
  - Hand: Basic interaction
  - Journal: Track story and clues
- **Boss Fights** - 3 unique bosses with 3 phases each
  - Root Warden (Level 1): Roots & projectiles
  - Grey Tide Witch (Level 2): Wave attacks
  - Hollow King (Level 3): Complex patterns
- **Game Mechanics**
  - Health system (5 HP default)
  - Invulnerability frames after damage
  - Boss phases based on health percentage
  - Particle effects for visual feedback
  - Collision detection
- **UI System**
  - HUD with HP, gems, current objective
  - Tool selection (1-4 keys)
  - Boss health bar during fights
- **Save System**
  - Automatic save after each level
  - Local browser storage
  - Resume functionality
- **Audio/Visuals**
  - Starry background
  - Animated tiles (trees, mushrooms, water, gems)
  - Character animation with 4 directions
  - Environmental variety per level

### 🎮 Level 1: The Withered Farm
- Corrupted farm with withered trees
- Quest: Collect 5 gems, defeat Root Warden
- Boss: Root Warden (HP: 80)
- Reward: Crystal Staff unlock

### 🎮 Level 2: The Drowned Market
- Flooded marketplace with water hazards
- Quest: Collect 5 gems, defeat Grey Tide
- Boss: Grey Tide Witch (HP: 120)
- Reward: Story progression

### 🎮 Level 3: The Hollow King's Keep
- Fortress with corrupted guardian
- Quest: Collect 5 gems, defeat Hollow King
- Boss: Hollow King (HP: 200)
- Reward: Game complete

### 🐛 Bug Fixes
- Map tile rendering alignment (camera translation)
- Boss phase transition display
- NPC dialog flow
- Projectile collision accuracy

### 📚 Documentation
- Gameplay guide (GAMEPLAY.md)
- Contributing guidelines (CONTRIBUTING.md)
- Code documentation (CLAUDE.md)
- Architecture guide (ARCHITECTURE.md)
- Development workflow (DEVELOPMENT.md)

### 🚀 Performance
- 60 FPS target maintained
- Optimized particle system
- Efficient collision detection
- Y-sorted painter's algorithm for rendering

---

## Version History

### v0.9.0
- Initial beta release
- Core gameplay loop
- Basic boss mechanics

### v0.5.0
- Early prototype with Level 1 only
- Basic player movement
- Simple projectile system

---

## Planning

### Next Version (v1.1.0) - Boss Enhancements
- [ ] Root Warden: Shockwave mechanic
- [ ] Grey Tide: Water puddle hazards
- [ ] Hollow King: Projectile splitting
- [ ] Difficulty scaling improvements

### Future (v1.2.0) - World Expansion
- [ ] Environmental structures (houses, wells, fences)
- [ ] Walking dust animations
- [ ] Mini animal companions
- [ ] Rock/sign animations

### Future (v2.0.0) - Major Features
- [ ] Modular code architecture
- [ ] Level editor
- [ ] Sound system
- [ ] More levels/chapters
- [ ] Mobile support

---

## Known Issues

### Current
- None known in stable version

### Previously Fixed
- ✅ Map tiles not aligned with camera
- ✅ Boss phases not displaying correctly
- ✅ NPC dialog not advancing

---

## Development Notes

- Game is single HTML file (~85KB)
- Pure JavaScript, no frameworks
- Browser local storage for persistence
- Canvas 2D rendering at 60 FPS
- Target browsers: Chrome, Firefox, Safari, Edge

---

**Last Updated:** 2026-04-23
**Stable Release:** v1.0.0
**Current Development:** Feature branches only
