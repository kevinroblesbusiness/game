# Commit Protocol - Zero Risk Development

## 🎯 Core Rule
**Every commit must leave the game in a 100% working state.**

If a commit breaks anything, it will be reverted immediately. No exceptions.

## 🔄 The Protocol (MUST follow exactly)

### Step 1: Before You Touch Code
```bash
# Verify you're on main with latest code
git status
git log --oneline -1

# Verify game works BEFORE changes
# Open: dist/starry-valley-ch2.html in browser
# Play through all 3 levels, verify no console errors
```

### Step 2: Create Feature Branch
```bash
git checkout -b feature/your-feature-name
```

### Step 3: Make ONE Change Only
- Edit **ONLY** `starry-valley-ch2.html`
- Make **ONE** logical change (e.g., "Add shockwave rendering")
- NO other changes
- NO cleanup while you're here
- NO refactoring
- NO comment improvements

### Step 4: Test Before Commit (CRITICAL)

**Open browser:**
```
file:///home/user/game/starry-valley-ch2.html
```

**Run this exact test sequence:**

```
□ Game loads (no blank screen)
□ No errors in console (F12 → Console tab)
□ Can move player (WASD/arrows)
□ Can collect gems (move over them)
□ Can talk to NPCs (press T)
□ Can use shield (press 2, then Space)
□ Can use crystal staff (press 3, then Space)
□ Can reach Level 1 boss
□ Boss appears and attacks
□ Can defeat boss and progress to Level 2
□ Level 2: same tests as Level 2
□ Level 3: same tests
□ Game completes without crashes
```

**If ANY test fails:** Stop. Do NOT commit. Revert changes.

### Step 5: Commit (Only If All Tests Pass)

```bash
git add starry-valley-ch2.html

git commit -m "Feature: Description of what changed

- Specific change 1
- Specific change 2
- What problem this solves"
```

**Commit message rules:**
- First line: SHORT description (under 50 chars)
- Blank line
- Bullet points of what changed
- Why this change matters

### Step 6: Final Verification (MANDATORY)

```bash
# Reload browser and test the EXACT feature you added
# Does it work as intended?
# Did it break anything?
```

### Step 7: Push (Only If Game Still Works)

```bash
git push -u origin feature/your-feature-name
```

## 🚨 If Something Breaks

**Immediately revert:**
```bash
# Go back to main
git checkout main

# Delete broken branch
git branch -D feature/your-feature-name

# Verify game works
# Open dist/starry-valley-ch2.html - confirm it's fine
```

## ❌ What NOT to Do

```
❌ "Add feature X and also refactor function Y"
❌ "Add feature X and fix unrelated bug"
❌ "Add feature X, improve comments, and clean up code"
❌ "Add multiple features in one commit"
❌ "Push without testing"
❌ "Commit and then test"
❌ "Trust that 'it probably works'"
```

## ✅ What TO Do

```
✅ Add feature X (nothing else)
✅ Test thoroughly
✅ Commit
✅ Verify test one more time
✅ Push
```

## 📊 Example Good Workflow

```bash
# 1. Start fresh from working version
git checkout main
git pull origin main

# 2. Create feature branch
git checkout -b feature/boss-shockwaves

# 3. Edit ONLY the game file - add shockwave creation
# (single logical change)

# 4. Test in browser
# - Game loads ✓
# - Boss 1 creates shockwaves ✓
# - Shockwaves damage player ✓
# - Can still beat boss ✓
# - No console errors ✓
# - All other features still work ✓

# 5. Commit
git add starry-valley-ch2.html
git commit -m "Add Root Warden shockwaves

- Boss creates expanding rings on attack
- Shockwaves deal damage on contact
- Shield blocks shockwaves
- Phase-dependent behavior"

# 6. Final test
# Reload browser - test shockwaves again ✓

# 7. Push
git push -u origin feature/boss-shockwaves

# 8. Create PR on GitHub
```

## 🔍 Revert Strategy

If a feature breaks the game:

**Option 1: Haven't pushed yet**
```bash
git reset --hard HEAD~1
# Back to working state, no commit made
```

**Option 2: Already pushed**
```bash
git revert HEAD
# Creates NEW commit that undoes changes
# Game back to working state
```

**Option 3: Multiple bad commits**
```bash
git checkout main
git pull origin main
# Back to stable version
# Delete bad branch
git branch -D feature/bad-feature
```

## 📝 Commit Checklist

Before hitting commit, verify:

- [ ] Changed ONLY `starry-valley-ch2.html`
- [ ] Made ONE logical change
- [ ] Tested game loads
- [ ] Tested new feature works
- [ ] Tested no console errors
- [ ] Tested old features still work
- [ ] Tested all 3 levels
- [ ] Can play through to completion
- [ ] Commit message is clear
- [ ] Ready to push

## 🎯 The Promise

If you follow this protocol:
- ✅ Every commit = working game
- ✅ Can revert any commit instantly
- ✅ Zero cascading bugs
- ✅ Only forward progress
- ✅ Safe to experiment

---

**This protocol is NOT optional. It prevents chaos.**

**Every commit must be safe to revert.**
