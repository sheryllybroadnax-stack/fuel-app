# FUEL - Personal Bible Study App

![Fuel Logo](fuel-logo.png)

**FUEL - My Life Fueled by God's WORD** is a transformational personal Bible study Progressive Web App (PWA) designed for deeper Scripture engagement with integrated tools for personal dictionary, prayer tracking, and Bible study notes.

## 📋 Table of Contents

- [Features](#-features)
- [Installation](#-installation)
- [Usage Guide](#-usage-guide)
- [Technical Details](#-technical-details)
- [Development](#-development)
- [Contributing](#-contributing)
- [License](#license)
- [Support](#support)

## ✨ Features

### 📖 Bible Reader
- **Complete KJV Bible** - All 66 books with chapter navigation
- **Multiple Versions** - KJV (default), ASV, Douay-Rheims American, Darby
- **Version Comparison** - Read primary and secondary versions side-by-side (desktop) or stacked (mobile)
- **Smart Loading** - Chapters load from public-domain dataset when online
- **Offline Access** - Bible data accessible offline after first load

### 📚 Personal Dictionary
- **Custom Entries** - Add words, definitions, topics, and study notes
- **Language Support** - Original language text (Greek/Hebrew) with transliteration
- **Strong's References** - Cross-reference Strong's concordance numbers
- **Favorites** - Bookmark important entries for quick access
- **Search History** - Up to 25 recent searches with quick-access buttons
- **Topic Organization** - Filter by 20+ Bible study categories

### 🙏 Prayer Tracker
- **Prayer Requests** - Track prayer requests with contact information
- **Follow-up Dates** - Set reminders for prayer follow-ups
- **Answered Prayers** - Record praise reports and answered prayers
- **Topical Scriptures** - Browse 30+ prayer topics with supporting scriptures
- **Printable Reports** - Generate reports of all, due/overdue, or answered prayers
- **Prayer Reminders** - Daily notifications for upcoming follow-ups

### 📖 The Filling Station
- **Personal Study Notes** - Create study notes for sermons, devotionals, and self-study
- **Study Categories** - Sermons, personal studies, Sunday school, conferences, book studies
- **Note Markers** - NTS, QTS, CTS, STLS symbols for quick notation
- **Tag System** - Add comma-separated tags to organize studies
- **Tag Filtering** - Search and filter all studies by selected tags
- **Printable Studies** - Export filtered or complete study notes

### 📝 Scripture Memory
- **Memory Practice** - Add verses to memorize with practice mode
- **Mastery Tracking** - Mark verses as mastered when complete
- **Topic Organization** - Organize memory verses by topic
- **Text Toggle** - Hide/show verse text during practice sessions

### 🎯 Daily Verse & Reminders
- **Daily Verse** - New inspiring verse each day
- **Customizable Time** - Set preferred reminder time (requires browser permission)
- **Push Notifications** - Receive reminders while app is running or in background

### 🎨 Themes & Interface
- **Night/Day Mode** - Toggle between light and dark themes
- **Persistent Settings** - App remembers your theme preference
- **Responsive Design** - Works seamlessly on phones, tablets, and desktop
- **Mobile Optimized** - Full-screen capable on mobile devices

### 📊 Entry Notes & Backup
- **Dated Notes** - Keep multiple dated study notes on dictionary entries
- **Google Drive Backup** - Automatic backup to Google Drive (with file sharing on mobile)
- **JSON Export** - Complete backup of all app data
- **Import Restore** - Restore from previous backups
- **Google Docs Export** - Convert prayer and study data to Word/HTML format

### 🗺️ Reference Tools
- **Bible Maps** - Interactive map sets (when online)
- **Bible Timeline** - Historical context for Bible periods
- **Study References** - Topical prayer scriptures organized by theme

## 🚀 Installation

### On Your Website (HTTPS Required)

1. **Upload Files** - Upload all app files to your HTTPS web server:
   ```
   index.html
   sw.js (service worker)
   manifest.webmanifest (PWA configuration)
   icon-192.png
   icon-512.png
   fuel-logo.png
   ```

2. **Verify HTTPS** - Your website must use HTTPS (required for PWA)

3. **Access the App** - Open your website URL in a browser

### Install on Phone

#### iPhone/iPad (Safari)
1. Open the app URL in Safari
2. Tap the **Share** button (↗ icon)
3. Select **Add to Home Screen**
4. Choose a name and tap **Add**
5. App appears on home screen as a full-screen app

#### Android (Chrome or Edge)
1. Open the app URL in Chrome or Edge
2. Tap the **menu** (⋮) icon
3. Select **"Install app"** or **"Add to Home screen"**
4. Confirm the installation
5. App appears on home screen with offline access

## 📖 Usage Guide

### Searching the Dictionary

1. Go to the **Dictionary** tab
2. Type a word, definition, topic, or Strong's number
3. Results filter in real-time
4. Tap an entry to view details
5. Tap "Notes" to add study notes to that entry

**Search History:** Recent searches appear as quick-access buttons. Tap a button to run that search again.

### Managing Prayer Requests

1. Go to the **Prayer** tab
2. Enter prayer title, description, and optional contact info
3. Set a follow-up date (optional)
4. Tap **Save Prayer**
5. View status in the follow-up summary
6. Mark prayers as answered when God responds

**Follow-ups:** Due/overdue prayers appear at the top of the list. Use the printable report to track all prayer activity.

### Creating Bible Study Notes

1. Go to **The Filling Station** tab
2. Select study type (sermon, personal study, etc.)
3. Enter topic, speaker, location, and Scripture references
4. Add study points, application, and prayer requests
5. Use note-marker buttons (NTS, QTS, CTS, STLS) for quick notation
6. Add tags for organizing multiple studies (e.g., "John", "Faith", "Prayer")
7. Tap **Save Study**

**Tags:** Use comma-separated tags (e.g., "Romans, Paul, Salvation"). Filter all studies by a selected tag to see related content.

### Reading the Bible

1. Go to the **Bible** tab
2. Select book from dropdown
3. Choose chapter
4. Tap verse to bookmark
5. Select alternate version to compare

**Comparison Mode:** On larger screens, primary and secondary versions appear side-by-side. On phones, scroll between them.

### Managing Memory Verses

1. Go to the **Memory** tab
2. Add Scripture reference and verse text
3. Add optional topic for organization
4. In practice mode, tap "Hide Text" to test recall
5. Mark verse as mastered when memorized

### Backing Up Your Data

**Google Drive Backup:**
- Tap **Back up to Google Drive**
- A timestamped JSON file uploads automatically
- On phones, choose Google Drive from share sheet

**JSON Export:**
- Tap **Export Backup** to download locally
- Save file for records or email backup

**Restore from Backup:**
- Tap **Restore from Backup**
- Select previously exported JSON file
- App loads all your data

**Tip:** Back up regularly, especially before major app updates or device changes.

## 🔧 Technical Details

### Architecture

- **Framework:** Vanilla JavaScript (no dependencies)
- **Storage:** Browser localStorage API (~5-10MB capacity)
- **Offline:** Service Worker (sw.js) for offline-first functionality
- **PWA:** Web App Manifest for installability
- **Bible API:** Public-domain KJV + optional external APIs for other versions

### Browser Compatibility

| Feature | Chrome | Firefox | Safari | Edge |
|---------|--------|---------|--------|------|
| Core App | ✅ | ✅ | ✅ | ✅ |
| Install to Home | ✅ | ✅ | ✅ (iOS 15.1+) | ✅ |
| Offline Mode | ✅ | ✅ | ✅ | ✅ |
| Notifications | ✅ | ✅ | ⚠️ (Limited) | ✅ |
| Google Drive | ✅ | ✅ | ✅ | ✅ |

### Data Storage

- **Location:** Browser localStorage on your device
- **Capacity:** Typically 5-10MB (varies by browser)
- **Privacy:** All data stays on your device
- **Sync:** Manual backup to Google Drive (requires Google account)

### Default Bible Study Reference

The app uses **The Open Bible, KJV** as the default study Bible:
- **Scripture Text:** KJV (public domain)
- **Study Notes:** Not bundled (proprietary content)
- **Topical Index:** Custom curated topics for prayer
- **Timeline:** Historical context for Bible periods

### File Structure

```
fuel-app/
├── index.html                 # Main PWA application
├── sw.js                      # Service worker for offline support
├── manifest.webmanifest       # PWA configuration
├── fuel-logo.png             # App branding logo
├── icon-192.png              # App icon (small)
├── icon-512.png              # App icon (large)
├── README.md                 # This documentation
├── CONTRIBUTING.md           # Contribution guidelines
├── LICENSE                   # MIT License
└── .gitignore               # Git configuration
```

## 👨‍💻 Development

### Local Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/sheryllybroadnax-stack/fuel-app.git
   cd fuel-app
   ```

2. **Serve locally (requires HTTPS for full PWA features):**
   ```bash
   # Using Python 3
   python -m http.server 8000
   
   # Using Node.js http-server
   npx http-server -p 8000 -c-1 --gzip
   
   # Using live-server
   npx live-server
   ```

3. **Access the app:**
   - Open `https://localhost:8000` (use HTTPS for PWA features)
   - For local testing without HTTPS, use `chrome://flags/#allow-insecure-localhost` (Chrome)

### Building & Deployment

#### GitHub Pages (Recommended)

The app automatically deploys to GitHub Pages when pushed to `main`:

1. Repository is already configured
2. Visit: `https://sheryllybroadnax-stack.github.io/fuel-app/`
3. Install the PWA from your browser's install menu

#### Custom Web Server

1. Upload all files to your HTTPS web server
2. Ensure MIME type for `.webmanifest` is `application/manifest+json`
3. Configure server to serve `index.html` for 404s (optional, for cleaner URLs)

#### Docker

```dockerfile
FROM nginx:alpine
COPY . /usr/share/nginx/html
EXPOSE 80
```

### Modifying the App

#### Adding Dictionary Entries

Edit `index.html` and modify the `defaultEntries` array (line ~19):

```javascript
const defaultEntries=[
  {
    id: 1,
    word: 'Your Word',
    definition: 'Your Definition',
    primary: 'KJV',
    category: 'Faith and Salvation',
    language: 'Greek',
    original: 'Greek text',
    translit: 'transliteration',
    strong: '1234',
    refs: 'John 3:16'
  },
  // Add more entries...
];
```

#### Adding Bible Versions

Add to the `versions` array (line ~16):

```javascript
const versions=['KJV','NKJV','NIV','ESV','NASB','NLT','CSB','AMP','ASV','WEB','YLT','YOUR_VERSION'];
```

Configure API endpoint in `fetchChapter()` function (line ~66).

#### Adding Prayer Categories

Modify the `prayerScriptures` array (line ~31):

```javascript
const prayerScriptures=[
  ['Your Category','Scripture References Separated; By Semicolon'],
  // Add more categories...
];
```

#### Customizing Colors

Edit CSS variables at the top of `index.html`:

```css
:root {
  --navy: #193b63;      /* Primary color */
  --gold: #d4a017;      /* Accent color */
  --cream: #fbf7ed;     /* Light background */
  --ink: #17202a;       /* Text color */
  --line: #ddd;         /* Border color */
}
```

### Testing

- **Offline:** Disable network in DevTools and verify app still works
- **Mobile:** Use Chrome DevTools device emulation
- **PWA:** Check Application tab in DevTools > Manifest, Service Workers
- **Performance:** Lighthouse audit in DevTools
- **Accessibility:** WAVE or Axe DevTools

## 🤝 Contributing

Contributions are welcome! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

### Quick Start for Contributors

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Make your changes
4. Test thoroughly on mobile and desktop
5. Commit with clear messages (`git commit -m 'Add feature description'`)
6. Push to your fork (`git push origin feature/your-feature`)
7. Open a Pull Request with description of changes

### Reporting Issues

Found a bug? [Open an issue](https://github.com/sheryllybroadnax-stack/fuel-app/issues) with:
- Clear title and description
- Steps to reproduce
- Expected vs. actual behavior
- Browser and device info

### Feature Requests

Have an idea? [Suggest a feature](https://github.com/sheryllybroadnax-stack/fuel-app/issues) with:
- Clear description of the feature
- How it improves Bible study
- Example use cases

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

**Summary:** You're free to use, modify, and distribute this app for personal and commercial use. Attribution is appreciated but not required.

## 🆘 Support

### Frequently Asked Questions

**Q: Is my data private?**
A: Yes! All data is stored locally on your device. The app never sends personal data to external servers except when you manually back up to Google Drive.

**Q: Can I use this offline?**
A: Yes! Once you open the app once, it caches and works offline. Bible chapters need internet to download, but your dictionary, prayers, and notes are always available.

**Q: How much can I store?**
A: Modern browsers allow 5-10MB of localStorage, which typically holds thousands of dictionary entries and study notes.

**Q: Can I sync across devices?**
A: Create a backup to Google Drive on one device, then restore it on another device.

**Q: Does this work on older phones?**
A: The app requires a modern browser (iOS 12+, Android 5+). Notification features require additional browser support.

### Getting Help

- 📖 Check the [Usage Guide](#-usage-guide) above
- 🐛 [Report a bug](https://github.com/sheryllybroadnax-stack/fuel-app/issues)
- 💡 [Request a feature](https://github.com/sheryllybroadnax-stack/fuel-app/issues)
- 📧 Contact the developer

### Bible Text Sources

- **KJV:** Public domain (1611 text)
- **Other versions:** Loaded from [Daily Bible API](https://dailybible.ca) when available and online
- **Study resources:** Original topical content with Scripture references

---

**May your life be fueled by God's WORD.** 📖✨

*Last Updated: September 2026*
