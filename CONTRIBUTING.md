# Contributing to FUEL App

Thank you for your interest in contributing to the FUEL Bible Study App! This document provides guidelines for contributing code, documentation, and ideas to this project.

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [How to Contribute](#how-to-contribute)
- [Development Setup](#development-setup)
- [Coding Standards](#coding-standards)
- [Submitting Changes](#submitting-changes)
- [Reporting Issues](#reporting-issues)
- [Feature Requests](#feature-requests)

## 📜 Code of Conduct

By participating in this project, you agree to abide by our Code of Conduct:

- Be respectful and inclusive
- Welcome people of all backgrounds and experience levels
- Focus on constructive criticism
- Respect different opinions and approaches
- Report inappropriate behavior

This is a faith-based project created for Bible study and spiritual growth. Please keep discussions professional and respectful of the project's spiritual purpose.

## 🚀 Getting Started

### Prerequisites

- GitHub account
- Git installed on your machine
- Basic understanding of HTML, CSS, and JavaScript
- Modern web browser (Chrome, Firefox, Safari, or Edge)

### Fork and Clone

1. Fork the repository on GitHub
2. Clone your fork locally:
   ```bash
   git clone https://github.com/YOUR-USERNAME/fuel-app.git
   cd fuel-app
   ```
3. Add upstream remote:
   ```bash
   git remote add upstream https://github.com/sheryllybroadnax-stack/fuel-app.git
   ```

## 🤝 How to Contribute

### Types of Contributions

We welcome contributions in these areas:

#### 🐛 Bug Fixes
- Identify and fix issues in existing functionality
- Improve error handling
- Optimize performance
- Fix UI/UX problems

#### ✨ New Features
- Add new Bible study tools
- Enhance existing features
- Improve user interface
- Add new supported Bible versions
- Enhance backup/restore functionality

#### 📚 Documentation
- Improve README and guides
- Add code comments
- Create tutorials or videos
- Translate documentation to other languages
- Document API endpoints or functions

#### 🎨 UI/UX Improvements
- Design improvements
- Accessibility enhancements
- Mobile responsiveness
- Theme customization
- User experience refinements

#### 🧪 Quality Assurance
- Test on different browsers
- Report edge cases
- Test on various devices
- Accessibility testing
- Performance optimization

## 🛠️ Development Setup

### Local Development

1. **Start a local server:**
   ```bash
   # Using Python 3
   python -m http.server 8000
   
   # Using Node.js http-server
   npx http-server -p 8000 -c-1 --gzip
   
   # Using live-server (auto-refresh)
   npx live-server --port=8000
   ```

2. **Access the app:**
   - Open `http://localhost:8000` in your browser
   - For PWA features, use HTTPS (see instructions below)

3. **Enable HTTPS for local testing:**
   ```bash
   # Generate self-signed certificate (Mac/Linux)
   openssl req -x509 -newkey rsa:4096 -nodes -out cert.pem -keyout key.pem -days 365
   
   # Then use with http-server
   npx http-server -p 8443 -c-1 --gzip --ssl --cert cert.pem --key key.pem
   ```

4. **Test in DevTools:**
   - Open Chrome DevTools (F12)
   - Application tab > Service Workers
   - Check offline mode works
   - Test localStorage operations

### Useful Tools

- **Chrome DevTools** - Built-in browser debugging
- **Lighthouse** - Performance and PWA audit
- **WAVE** - Accessibility testing
- **Axe DevTools** - Advanced accessibility checking
- **VS Code** - Code editor with helpful extensions

## 💻 Coding Standards

### JavaScript

1. **Use vanilla JavaScript** - No external frameworks/libraries unless approved
2. **Naming conventions:**
   - Functions: camelCase (`saveEntry`, `renderPrayers`)
   - Variables: camelCase (`searchHistory`, `entryNotes`)
   - Constants: UPPER_SNAKE_CASE (`DEFAULT_ENTRIES`, `BIBLE_BOOKS`)
   - Private methods: prefix with underscore (`_parseBackup`)

3. **Code organization:**
   ```javascript
   // 1. Constants at top
   const CATEGORIES = ['Faith', 'Prayer'];
   
   // 2. Global variable initialization
   let entries = [];
   
   // 3. Initialize function called on load
   function init() { }
   
   // 4. Main functions
   function saveEntry(data) { }
   
   // 5. Helper/utility functions
   function esc(s) { }
   ```

4. **Comments:**
   ```javascript
   // Use single-line comments for explanations
   // Explain WHY, not WHAT the code does
   
   // ❌ Avoid: "Add 1 to counter"
   // ✅ Better: "Increment counter to track iterations"
   
   /* Use multi-line for complex sections */
   ```

5. **Error handling:**
   ```javascript
   try {
     const data = JSON.parse(backup);
     entries = data.entries;
   } catch (e) {
     alert('Backup format is invalid');
     console.error('Restore failed:', e);
   }
   ```

### HTML/CSS

1. **Use semantic HTML:**
   ```html
   ✅ <section id="bible">...</section>
   ✗ <div class="bible">...</div>
   
   ✅ <button onclick="savePrayer()">Save</button>
   ✗ <div onclick="savePrayer()">Save</div>
   ```

2. **CSS organization:**
   - Group related styles
   - Use CSS variables for colors/spacing
   - Mobile-first approach
   - Keep specificity low

3. **Accessibility:**
   - Use proper heading hierarchy (h1 > h2 > h3)
   - Add `alt` text to images
   - Use `label` elements with form inputs
   - Ensure color contrast meets WCAG standards

## 📝 Submitting Changes

### Step 1: Create a Branch

```bash
# Fetch latest from upstream
git fetch upstream

# Create feature branch
git checkout -b feature/description-of-feature upstream/main

# Or for bug fixes
git checkout -b fix/description-of-bug upstream/main
```

### Step 2: Make Changes

1. Make your changes locally
2. Test thoroughly
3. Commit with clear, descriptive messages:
   ```bash
   git commit -m "Add feature: Brief description of what was added"
   git commit -m "Fix: Brief description of what was fixed"
   git commit -m "Docs: Update README with installation steps"
   ```

4. Use meaningful commit messages:
   ```
   ✅ Good:
   - "Add Google Drive backup button to backup panel"
   - "Fix: Prayer list not displaying due dates"
   - "Improve mobile responsiveness on prayer screen"
   
   ❌ Avoid:
   - "fix stuff"
   - "update"
   - "WIP"
   ```

### Step 3: Sync with Upstream

```bash
git fetch upstream
git rebase upstream/main
```

### Step 4: Push and Create Pull Request

```bash
git push origin feature/description-of-feature
```

Then on GitHub:

1. Go to your fork
2. Click "Compare & pull request"
3. Fill in the Pull Request template with:
   - **Title:** Brief description of changes
   - **Description:** What changed and why
   - **Testing:** How to test these changes
   - **Screenshots:** Before/after if UI changes
   - **Checklist:** Mark completed items

### PR Description Template

```markdown
## Description
Brief overview of the changes

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Documentation
- [ ] UI/UX improvement
- [ ] Performance improvement

## Testing Instructions
1. Step to reproduce/test
2. Another step
3. Expected result

## Screenshots (if applicable)
[Before/After images]

## Checklist
- [ ] I tested this on mobile
- [ ] I tested this on desktop
- [ ] Code follows project style guidelines
- [ ] I added/updated relevant documentation
- [ ] No breaking changes
- [ ] Works offline where applicable
```

### Step 5: Respond to Review Feedback

1. Review maintainer comments
2. Make requested changes
3. Commit changes: `git commit -m "Address PR review feedback"`
4. Push again: `git push origin feature/description-of-feature`
5. Maintainer will merge when satisfied

## 🐛 Reporting Issues

### Before Reporting

- Search existing issues to avoid duplicates
- Check if issue has been fixed in latest version
- Test in multiple browsers
- Note your browser version and OS

### Creating an Issue

Click "New Issue" and use the appropriate template:

#### Bug Report

```markdown
## Description
Clear description of the bug

## Steps to Reproduce
1. Go to ...
2. Click on ...
3. See error

## Expected Behavior
What should happen

## Actual Behavior
What actually happens

## Environment
- Browser: Chrome 120
- OS: Windows 11
- Device: Desktop

## Screenshots/Logs
[Screenshots, error messages, console logs]

## Additional Context
Any other relevant information
```

#### Feature Request

```markdown
## Description
Clear description of requested feature

## Use Case
Why this feature would be helpful

## Proposed Solution
Your idea for how to implement it

## Alternative Solutions
Other approaches you've considered

## Additional Context
Examples from other apps or references
```

## 💡 Feature Requests

### Before Suggesting

- Check existing issues and discussions
- Ensure feature aligns with project goals (Bible study focus)
- Consider impact on app size and performance
- Think about mobile device limitations

### Feature Discussion

1. Create an issue with "Feature Request" label
2. Describe the problem it solves
3. Provide use cases and examples
4. Engage with maintainers and community feedback

## 📦 Review Process

### What Maintainers Look For

- ✅ Code quality and standards
- ✅ Thorough testing
- ✅ Documentation
- ✅ No breaking changes
- ✅ Mobile compatibility
- ✅ Offline functionality where relevant
- ✅ Accessibility compliance
- ✅ Clear commit messages

### Timeline

- **Small fixes:** 1-3 days
- **Features:** 1-2 weeks
- **Documentation:** Same day

## 🎯 Development Tips

### Testing Checklist

Before submitting a PR, verify:

- [ ] Feature works on mobile (Portrait and landscape)
- [ ] Feature works on desktop
- [ ] Works offline (after service worker loads)
- [ ] No console errors
- [ ] localStorage operations work
- [ ] Responsive design is maintained
- [ ] Accessibility (keyboard navigation, screen reader)
- [ ] Performance is acceptable

### Common Tasks

**Add a new dictionary category:**
```javascript
// In index.html, line ~17
const categories=['Attributes of God', 'Bible Prophecy', ..., 'Your New Category'];
```

**Add a Bible version:**
```javascript
// In index.html, line ~16
const versions=['KJV', 'NKJV', ..., 'YOUR_VERSION'];
// Add API configuration in fetchChapter() function
```

**Add a prayer topic:**
```javascript
// In index.html, line ~31
const prayerScriptures=[
  ['Your Topic', 'Scripture References; Separated; By Semicolon'],
  ...
];
```

**Modify app colors:**
```css
/* In index.html, :root section */
:root {
  --navy: #193b63;      /* Change hex color */
  --gold: #d4a017;
  --cream: #fbf7ed;
  --ink: #17202a;
  --line: #ddd;
}
```

## 🤔 Questions?

- Check the [README.md](README.md) for project info
- Review existing issues and discussions
- Ask in a new discussion if needed
- Comment on relevant issues for clarification

## 🙏 Thank You

We deeply appreciate your contributions to FUEL! Whether it's code, documentation, bug reports, or ideas, you're helping others deepen their relationship with God's WORD.

---

**May your contributions be blessed!** 📖✨

*Last Updated: September 2026*
