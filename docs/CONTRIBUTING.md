# Contributing to Starry Valley

Thanks for wanting to help! Here's how to contribute to the game.

## 🎯 Ways to Contribute

1. **Report Bugs** - Found something broken? Create an issue
2. **Suggest Features** - Have an idea? Open an issue to discuss
3. **Write Documentation** - Help others understand the code
4. **Code Improvements** - Fix bugs or improve performance
5. **Content** - Create new levels, NPCs, or story content

## 🚀 Getting Started

### Prerequisites
- A GitHub account
- A code editor (VS Code, Sublime Text, etc.)
- Git installed on your computer

### Step 1: Fork the Repository
1. Click the **Fork** button on GitHub
2. This creates your own copy of the project

### Step 2: Clone Your Fork
```bash
git clone https://github.com/YOUR-USERNAME/game.git
cd game
```

### Step 3: Create a Feature Branch
```bash
git checkout -b feature/your-feature-name
```

Examples:
- `feature/add-level-4`
- `fix/boss-health-bar`
- `docs/improve-readme`

### Step 4: Make Your Changes
1. Open `starry-valley-ch2.html` in your editor
2. Make your changes
3. Test in your browser

### Step 5: Commit Your Work
```bash
git add .
git commit -m "Clear description of what you changed"
```

Good commit messages:
- ✅ `Add new NPC dialogue for Level 2`
- ✅ `Fix camera misalignment bug`
- ✅ `Improve gem collection feedback`
- ❌ `fixed stuff`
- ❌ `changes`

### Step 6: Push to Your Fork
```bash
git push origin feature/your-feature-name
```

### Step 7: Create a Pull Request
1. Go to your fork on GitHub
2. Click **Compare & Pull Request**
3. Add a clear title and description
4. Click **Create Pull Request**

## 📝 Pull Request Guidelines

Your PR description should include:

```markdown
## What does this PR do?
Brief description of changes

## Why?
Why is this change needed?

## Testing
How did you test this?

## Screenshots
If UI change, include before/after screenshots
```

## 🔍 Code Style

### Variable Names
- `playerX` not `px` (clear names!)
- `gemCount` not `gc`
- `tileSize` not `T` (except the constant)

### Comments
- Add comments for complex logic
- Explain the "why", not the "what"
- Keep comments up to date with code

### Formatting
- Use 2 spaces for indentation (not tabs)
- Keep lines under 100 characters
- One blank line between functions

## ✅ Quality Checklist

Before submitting your PR:

- [ ] Tested the game in browser
- [ ] No console errors (check F12 → Console tab)
- [ ] Followed code style guidelines
- [ ] Added comments for complex logic
- [ ] Commit message is clear
- [ ] Works on Chrome and Firefox

## 🐛 Reporting Bugs

Create an Issue with:

1. **Title**: Clear, concise description
2. **Steps to Reproduce**: 
   - "Open game"
   - "Move to location X"
   - "Observe: [what happens]"
3. **Expected Behavior**: What should happen
4. **Actual Behavior**: What actually happens
5. **Browser**: Chrome, Firefox, Safari, etc.

Example:
```
Title: Boss health bar doesn't update in Level 3

Steps to reproduce:
1. Reach Level 3 boss
2. Attack with crystal staff
3. Health bar shows no damage

Expected: Health bar should decrease
Actual: Health bar stays full

Browser: Chrome 90
```

## 💡 Feature Requests

Have an idea? Open an Issue:

```
Title: Request - Add sound effects

Description:
It would be cool to add sound effects for:
- Gem collection
- Boss hits
- Level complete

I can help with this!
```

## 📖 Documentation

Want to improve docs? 

1. Edit `README.md`, `CLAUDE.md`, or files in `docs/` folder
2. Keep it clear and beginner-friendly
3. Use examples when possible
4. Include links to resources

## 🎨 Adding New Content

### New Level
1. Add entry to `LEVELS` array in the HTML
2. Define map size, colors, NPCs, items
3. Test thoroughly
4. Document in PR description

### New NPC
1. Add to appropriate level's `npcs` array
2. Create dialogue in `DIALOGS` (around line 900+)
3. Add drawing function if custom appearance needed

### New Item/Mechanic
1. Update game state in `G` object
2. Add logic to `update()` function
3. Add drawing logic to `render()` function
4. Test collision and interaction

## 🤝 Review Process

After you submit a PR:

1. The project owner will review
2. They might ask for changes
3. Make requested changes and push again
4. PR merges once approved

Don't worry about perfect code - we're here to help improve it together!

## 📚 Resources

- [GitHub Guides](https://guides.github.com/) - Learn Git & GitHub
- [How to Write Commit Messages](https://www.freecodecamp.org/news/writing-good-commit-messages-a-practical-guide/)
- [Code Style Guide](https://google.github.io/styleguide/htmlcssguide.html)

## ❓ Questions?

- Read [CLAUDE.md](../CLAUDE.md) for code documentation
- Check existing Issues and PRs
- Ask in PR comments - we're happy to help!

## 🎉 Thank You!

Every contribution matters. Whether it's a bug fix, new feature, or better documentation, you're helping make Starry Valley better for everyone!

---

**Ready to contribute?** Start with a small bug fix or documentation improvement to get familiar with the process!
