# Contributing to zKillboard Loot Tracker

Thank you for your interest in contributing to zKillboard Loot Tracker! We welcome contributions from the community. This document provides guidelines and instructions for contributing.

## Code of Conduct

Be respectful and inclusive. We're all here to make EVE Online better.

## How to Contribute

### Reporting Bugs

If you find a bug, please [open an issue](https://github.com/yourusername/zkillboard-loot-tracker/issues) with:

1. **Clear title** - What's broken?
2. **Description** - What should happen vs what actually happens?
3. **Steps to reproduce** - How do you make it happen?
4. **Environment** - Browser, OS, version
5. **Screenshots** - If applicable

Example:
```
Title: ISK splits not calculating correctly with odd fleet sizes

Description:
When I have 7 pilots and 1B ISK to split, the calculator shows 142857142 ISK 
per pilot instead of 142857143. Some pilots get short-changed.

Steps:
1. Add kills totaling 1B ISK
2. Set fleet size to 7
3. Check the split result

Browser: Chrome 120, Windows 10
```

### Suggesting Enhancements

Have an idea? [Open an issue](https://github.com/yourusername/zkillboard-loot-tracker/issues) with the label "enhancement":

1. **What's the feature?** - Clear description
2. **Why do you need it?** - Use case explanation
3. **How would you use it?** - Example workflow
4. **Alternatives** - Any workarounds currently?

Example:
```
Title: Add ability to track damage percentage for pilot contributions

Description:
Currently we split ISK equally. It would be great to track what percentage 
of damage each pilot did so we can reward high-damage pilots more.

Why: This would be more fair for complex operations where some pilots contribute 
more damage than others.

How: Maybe add a "Damage %" field for each pilot?

Alternatives: Currently we split by hand based on damage reports.
```

## Development Workflow

### Getting Started

1. **Fork** the repository
   ```bash
   # Click "Fork" on GitHub
   ```

2. **Clone** your fork
   ```bash
   git clone https://github.com/YOUR_USERNAME/zkillboard-loot-tracker.git
   cd zkillboard-loot-tracker
   ```

3. **Create a branch**
   ```bash
   git checkout -b feature/my-awesome-feature
   # or
   git checkout -b bugfix/issue-description
   ```

4. **Make changes** to `eve_loot_tracker.html`

5. **Test locally**
   - Open the HTML file in your browser
   - Test in Chrome, Firefox, Safari if possible
   - Test on mobile if the feature is user-facing
   - Use the browser developer tools (F12) to check for errors

6. **Commit** with clear messages
   ```bash
   git add eve_loot_tracker.html
   git commit -m "Add damage percentage tracking feature"
   ```

7. **Push** to your fork
   ```bash
   git push origin feature/my-awesome-feature
   ```

8. **Open a Pull Request**
   - Go to GitHub and click "New Pull Request"
   - Fill out the PR template
   - Link any related issues
   - Wait for review!

### Branch Naming

- `feature/description` - New features
- `bugfix/description` - Bug fixes
- `docs/description` - Documentation updates
- `style/description` - Code style improvements

### Commit Messages

Write clear commit messages:

```
Add damage percentage tracker to pilots

- Add damage % input field to pilot roster
- Calculate weighted splits based on damage
- Update export to include damage stats
- Add tests for damage calculation

Fixes #123
```

Good commit messages:
- Are in imperative mood ("Add" not "Added")
- Explain what and why, not just what
- Reference related issues
- Are specific, not vague

## Code Style

### General Guidelines

- Keep the **single-file structure** - Don't split into multiple files
- Maintain **zkillboard aesthetic** - Dark red, crisp borders, no rounded corners
- Use **vanilla JavaScript** - No frameworks or external libraries
- Comment complex functions
- Keep code readable over clever

### JavaScript Style

```javascript
// Use descriptive function names
function addKill() {
    // Clear comments for complex logic
    const killID = input.value.trim();
    
    // Validate before processing
    if (!killID) {
        showMessage('Enter a kill ID', 'error');
        return;
    }
    
    // Use const/let, not var
    const killObj = {
        id: killID,
        value: totalValue
    };
    
    // Update UI after data changes
    updateDisplay();
}
```

### HTML Structure

Keep the tab system organized:
```html
<div id="tabname" class="tab-content active">
    <h2>Tab Title</h2>
    <!-- Tab content here -->
</div>
```

### CSS Classes

Follow the existing naming:
- `.panel` - Main content boxes
- `.stat-block` - Statistics displays
- `.kill-item` - Kill list items
- `.form-group` - Input groups
- Use hyphens for multi-word classes

## Testing Checklist

Before submitting a PR, test:

- [ ] Feature works as intended
- [ ] No console errors (F12)
- [ ] Works in Chrome
- [ ] Works in Firefox
- [ ] Works on mobile view (test with DevTools)
- [ ] UI matches zkillboard aesthetic
- [ ] No layout shifts or broken borders
- [ ] Related features still work
- [ ] Export function still works if modified

### Manual Testing Scenarios

Add some test data:
```
Kill 1: 100M ISK
Kill 2: 250M ISK
Loss: 50M ISK
Profit: 300M ISK
Fleet size: 4 pilots
Expected per pilot: 75M ISK
```

Test edge cases:
- 0 kills
- Very large ISK amounts (999B+)
- Odd numbers (7 pilots splitting 1B)
- Mobile screen sizes
- Fast clicking / rapid additions

## Pull Request Process

When you open a PR:

1. **Write a description** - What does this change do?
2. **Reference issues** - "Fixes #123"
3. **List changes** - Bullet points of what changed
4. **Test evidence** - "Tested on Chrome/Firefox/Safari"
5. **No breaking changes** - Maintain backward compatibility

Example PR:
```markdown
## Description
Adds ability to track damage percentage for each pilot in the fleet. This allows 
more fair ISK splits based on contribution rather than equal shares.

## Changes
- Add "Damage %" input field to pilot roster
- Calculate weighted ISK split based on damage %
- Update export to include damage contributions
- Add visual indicator for top damage dealer

## Related Issues
Fixes #45
Related to #67

## Testing
- Tested on Chrome 120 (Windows 10)
- Tested on Firefox 121 (macOS)
- Tested on Safari 17 (iPhone)
- Verified export includes damage stats
- Edge cases tested: 0% damage, 100% damage, uneven percentages

## Screenshots
[Attach any screenshots showing the new feature]
```

## Review Process

Maintainers will:
1. Review code for quality and style
2. Check that it works as intended
3. Verify it matches the zkillboard aesthetic
4. Test on multiple browsers
5. Request changes if needed
6. Merge when approved!

Please be patient - reviews may take a few days. We volunteer our time. 🙏

## What Happens After Merge

Once your PR is merged:
- Your code becomes part of the project
- You're listed as a contributor
- Your feature will be live for all users
- Thank you! 🎉

## Questions?

- **How do I run this locally?** - Open the HTML file in a browser, that's it!
- **How do I debug?** - Press F12 to open DevTools, check Console for errors
- **Can I test my changes?** - Yes, add test kills with IDs from zkillboard
- **Need help?** - Ask in the issue comments, we're happy to help!

## Areas We're Looking For Help

- **Bug fixes** - Got a fix? Send a PR!
- **Performance** - Can you optimize calculations?
- **UI/UX** - Ideas for better usability?
- **Documentation** - Better explanations?
- **Testing** - Found edge cases?
- **Features** - Have a great idea?

## Recognition

Contributors are awesome! We recognize you by:
- Adding your name to the contributors list
- Listing you in the README
- Giving you credit in the commit history

## License

By contributing, you agree your code will be licensed under MIT License (same as the project). See [LICENSE](LICENSE) file.

---

Thank you for making zKillboard Loot Tracker better! 🚀⚔

Questions? Open an issue or ask in discussions. Happy coding!
