# Development Workflow Guide

## 🚦 Golden Rules

1. **ALWAYS START FROM MAIN** - Main branch is the stable, working version
2. **ONE FEATURE AT A TIME** - Add one small feature, test, commit, then move to next
3. **TEST BEFORE COMMITTING** - Load game in browser, verify it works
4. **SMALL COMMITS** - Each commit should be one logical change
5. **KEEP DIST UPDATED** - Copy tested code to `/dist/` as the "release" version

## 📋 Development Checklist

### Before You Start
- [ ] You're on `main` branch
- [ ] Latest code is pulled (`git pull origin main`)
- [ ] Game loads and runs (test in browser)
- [ ] No console errors (F12 → Console)

### Adding a Feature (Step by Step)

#### 1. Create Feature Branch
```bash
git checkout main
git pull origin main
git checkout -b feature/descriptive-name
```

**Branch naming convention:**
- `feature/boss-shockwaves`
- `fix/camera-jitter`
- `improvement/ui-layout`
- `docs/game-guide`

#### 2. Make ONE Small Change
- Edit **only the working game file**: `starry-valley-ch2.html`
- Make a single, focused change (not multiple features)
- Example: "Add shockwave creation in fireAttack()"

#### 3. Test in Browser
```bash
# Open the file in browser
# In Chrome/Firefox address bar:
file:///home/user/game/starry-valley-ch2.html
```

**Test checklist:**
- [ ] Game loads
- [ ] No red errors in console (F12)
- [ ] Feature works as intended
- [ ] Existing features still work
- [ ] Game runs smoothly (no lag)

#### 4. Commit with Clear Message
```bash
git add starry-valley-ch2.html
git commit -m "Add shockwave mechanic to Root Warden boss

- Creates expanding rings on attack
- Phase 1: 1 shockwave at 2px/frame
- Phase 2: 2 shockwaves at 3px/frame
- Shockwaves deal 1 damage, shield blocks them"
```

**Good commit messages:**
- First line: What was changed (imperative mood)
- Blank line
- Details about the change
- Bullet points for complex changes

#### 5. Test Again
```bash
git log --oneline    # Verify commit was made
# Reload game in browser and test again
```

#### 6. Push and Create PR
```bash
git push -u origin feature/your-feature-name
# Then create PR on GitHub
```

### Code Review Checklist

Before approving a PR:
- [ ] Code follows existing patterns
- [ ] No syntax errors
- [ ] Game loads without crashing
- [ ] Feature works correctly
- [ ] Existing features not broken
- [ ] Commit message is clear
- [ ] Changes are focused (not "while I was here" changes)

## 🐛 If Something Breaks

### Option 1: Quick Fix
If you broke it on current branch:
```bash
# Revert the last commit
git reset --hard HEAD~1
# Fix the issue
# Commit again
```

### Option 2: Revert to Main
If multiple commits are broken:
```bash
git checkout main
git pull origin main
# Start fresh with new branch
git checkout -b feature/new-attempt
```

## 📊 Commit Size Guide

### ✅ Good Commits (Small, Focused)
- "Add shockwave rendering"
- "Fix boss collision detection"
- "Reduce dust animation frequency"

### ❌ Bad Commits (Too Big)
- "Add all boss improvements" (includes shockwaves, puddles, splitting)
- "Update everything" (multiple unrelated changes)

## 🔍 Testing Thoroughly

### Essential Tests
1. **Game Loads**
   - Open `/dist/starry-valley-ch2.html` in browser
   - Should reach title screen
   - No errors in console

2. **Level Progression**
   - Level 1: Move around, collect gems, defeat boss
   - Level 2: Same
   - Level 3: Same

3. **New Feature**
   - Specifically test the feature you added
   - Try edge cases (minimum, maximum values)
   - Test with shield, test without shield

4. **Existing Features**
   - Player movement still works
   - NPCs can still be talked to
   - Gems still collectible
   - Boss still defeatable
   - UI still visible and functional

## 📁 When to Update /dist/

Only copy to `/dist/` when:
- ✅ All tests pass
- ✅ Feature is complete and working
- ✅ No console errors
- ✅ Merged to main branch

**Don't copy to /dist/ if:**
- ❌ Still in development
- ❌ On a feature branch
- ❌ Untested code

## 🎯 Current Focus Areas

### High Priority
- Boss mechanics (shockwaves, unique attacks)
- Performance optimization
- Game balance (difficulty progression)

### Medium Priority
- Environmental variety
- More NPCs/dialog
- Visual polish

### Low Priority
- Sound effects
- Advanced animations
- Mobile support

## 💬 Communication

- Keep commits focused on ONE thing
- Write clear commit messages
- Document WHY you made changes, not just WHAT
- If stuck, create an issue describing the problem

## 📞 If You Need Help

1. Check `CLAUDE.md` for code documentation
2. Check `CONTRIBUTING.md` for contribution guidelines
3. Look at recent commits to see coding patterns
4. Test small changes first before big ones

---

**Remember: Small, careful changes are better than big risky ones!**
