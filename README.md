# ⚔ zKillboard Loot Tracker

A free, open-source web application for EVE Online gate campers to track killmails, calculate loot totals, and split ISK with their fleet.

![Status](https://img.shields.io/badge/status-active-brightgreen)
![License](https://img.shields.io/badge/license-MIT-blue)
![Version](https://img.shields.io/badge/version-2.0-red)

## 📋 Overview

**zKillboard Loot Tracker** is a real-time fleet ISK calculator designed specifically for EVE Online PvP operations. Whether you're running gate camps, roams, or coordinated attacks, this tool lets you:

- Add kills directly from zkillboard links
- Track losses to calculate net profit
- See detailed loot breakdowns by item type
- Calculate ISK splits with automatic fleet accounting
- Apply corp taxes and calculate ISK/hour efficiency
- Save and compare multiple fleet sessions
- Export detailed reports for fleet distribution

No installation required. Just open the HTML file in any modern browser and start tracking kills.

## ✨ Features

### Core Features
- **Automatic Killmail Fetching** - Paste zkillboard links or kill IDs to instantly fetch data
- **Real-Time ISK Calculation** - Totals update as you add kills
- **Loss Tracking** - Account for friendly losses to calculate actual profit
- **Loot Breakdown** - Visual bar chart showing top 50 looted items by value
- **Fleet Management** - Add pilot names and track fleet composition
- **Manual Entry** - Add kills when the API is slow or unavailable

### Advanced Calculators
- **ISK Split Calculator** - Automatically divides profit among fleet members
- **Tax Calculator** - Account for corp/alliance taxes with separate payouts
- **ISK/Hour Calculator** - Track efficiency based on operation duration
- **Session Saver** - Save gate camp sessions and compare performance over time

### Data Management
- **Export Reports** - Download detailed text reports for fleet distribution
- **Session History** - Keep records of past operations with stats
- **Zero Dependencies** - Runs entirely in your browser with no backend needed

## 🚀 Quick Start

### Installation

1. **Download the file:**
   ```bash
   git clone https://github.com/yourusername/zkillboard-loot-tracker.git
   cd zkillboard-loot-tracker
   ```

2. **Open in browser:**
   - Double-click `eve_loot_tracker.html` 
   - Or drag it into your browser
   - That's it! No server setup needed.

### Usage

#### Adding Kills

1. Go to the **Kills** tab
2. Paste a zkillboard link: `https://zkillboard.com/kill/12345678/`
3. Or just paste the kill ID: `12345678`
4. Click **Add Kill**
5. Watch the totals update in real-time

#### Recording Losses

1. Switch to the **Losses** tab
2. Enter the ship name, ISK value, and pilot
3. Click **Add Loss**
4. Losses automatically subtract from your profit total

#### Viewing Loot Breakdown

1. Go to the **Loot Breakdown** tab
2. See a visual chart of all items dropped, sorted by value
3. Great for identifying high-value loot types

#### Managing Your Fleet

1. Open the **Pilots** tab
2. Add each fleet member's character name
3. The app automatically calculates ISK per pilot
4. Reset contributions between ops

#### Manual Kill Entry

1. Use the **Manual Entry** tab for kills that didn't fetch from the API
2. Enter victim, ship type, location, and ISK value
3. Useful during high-activity periods when zkillboard is slow

#### Calculating ISK Splits

In the right panel:
- **Fleet Size** - Number of pilots (auto-calculates per-pilot share)
- **Tax %** - Apply corp tax (default 10%)
- **Duration** - Operation length to calculate ISK/hour

Example: 5B ISK looted, 5 pilots, 10% tax:
- Total: 5B ISK
- Corp Tax: 500M ISK
- Fleet Share: 4.5B ISK
- Per Pilot: 900M ISK

#### Saving Sessions

1. Go to the **Sessions** tab
2. Name your gate camp (e.g., "Amarr Gate Camp - Tuesday")
3. Click **Save Current Session**
4. View all previous sessions with their stats
5. Compare performance across operations

#### Exporting Results

1. Click the **Export** button
2. Get a formatted text file with:
   - Full kill list with values and times
   - All losses recorded
   - Fleet roster
   - Tax breakdown
   - Per-pilot ISK share

Share this with your fleet for easy wallet transfers!

## 🛠️ Technology Stack

- **HTML5** - Structure
- **CSS3** - Styling (zkillboard aesthetic)
- **Vanilla JavaScript** - All functionality, no frameworks
- **zKillboard API** - Real-time killmail data fetching

**Browser Support:**
- Chrome/Chromium 90+
- Firefox 88+
- Safari 14+
- Edge 90+

## 📊 API Usage

This project uses the **free, public zKillboard API**:

```javascript
// Fetches killmail data for a specific kill ID
fetch(`https://zkillboard.com/api/killID/{killID}/`)
```

**Rate Limits:** None enforced by zkillboard for reasonable usage
**Terms:** Free public API, no key required

## 🎨 Design

The UI matches zkillboard's signature dark red aesthetic:
- Deep black backgrounds (#0a0a0a)
- Crimson red accents (#c41e3a)
- Bright red glowing text shadows
- Sharp, angular borders (no rounded corners)
- Impact font for main title

All styling is responsive and works great on mobile/tablet for in-fleet use.

## 💾 Data Storage

**Local Storage Only:**
- All data stays in your browser
- Nothing is sent to external servers (except zkillboard API)
- No cookies or tracking
- Your data is private by default
- Clears when you close the tab or use "Clear All"

**Optional Enhancement:** Data persists in browser storage during your session. For permanent storage across browser closures, deploy to a server with a backend database (see Development section).

## 🔧 Development

### Setup
```bash
git clone https://github.com/yourusername/zkillboard-loot-tracker.git
cd zkillboard-loot-tracker
# No dependencies to install!
```

### File Structure
```
zkillboard-loot-tracker/
├── eve_loot_tracker.html    # Main application (single file)
├── README.md                 # This file
├── LICENSE                   # MIT License
└── CONTRIBUTING.md           # Contribution guidelines
```

### Making Changes
1. Edit `eve_loot_tracker.html` directly
2. Test in your browser (F5 to refresh)
3. Commit and push changes
4. Submit a pull request

### Adding Features
The app is organized by function in the JavaScript section:
- **Kill Management** - `addKill()`, `fetchKillmail()`, `removeKill()`
- **Loss Management** - `addLoss()`, `removeLoss()`, `updateLossesList()`
- **Calculations** - `calculateSplit()`, `getTotalProfit()`, `formatISK()`
- **Sessions** - `saveSession()`, `updateSessionsList()`
- **Export** - `exportResults()`

### Possible Enhancements
- [ ] Persistent data storage with IndexedDB
- [ ] Backend API for cross-device syncing
- [ ] Kill statistics dashboard with graphs
- [ ] Damage percentage tracking for pilot contributions
- [ ] Automated wallet calculator (eve-esi integration)
- [ ] Mobile app version
- [ ] Dark/light theme toggle
- [ ] Multiple language support

## 📝 License

MIT License - feel free to use, modify, and distribute this project.

See [LICENSE](LICENSE) file for details.

## 🤝 Contributing

Contributions are welcome! Here's how:

1. **Fork** the repository
2. **Create a branch** for your feature (`git checkout -b feature/amazing-feature`)
3. **Make changes** to `eve_loot_tracker.html`
4. **Test thoroughly** in multiple browsers
5. **Commit** with clear messages (`git commit -m 'Add amazing feature'`)
6. **Push** to your branch (`git push origin feature/amazing-feature`)
7. **Open a Pull Request** with description of changes

### Guidelines
- Keep the single-file structure
- Maintain zkillboard aesthetic
- Test on mobile and desktop
- Update README if adding major features
- No external dependencies

## 🐛 Bug Reports

Found a bug? [Open an issue](https://github.com/yourusername/zkillboard-loot-tracker/issues) with:
- Browser and version
- Steps to reproduce
- Expected vs actual behavior
- Screenshots if applicable

## 📦 Deployment

### Deploy to GitHub Pages (Free)

1. Push code to GitHub
2. Go to **Settings → Pages**
3. Select **main** branch as source
4. Your site will be live at: `yourusername.github.io/zkillboard-loot-tracker`

### Deploy to Netlify (Free)

1. Go to [netlify.com](https://netlify.com)
2. Click "New site from Git"
3. Connect GitHub repo
4. Set publish directory to root
5. Deploy!

### Deploy to Vercel (Free)

1. Go to [vercel.com](https://vercel.com)
2. Import GitHub repository
3. Deploy automatically
4. Share link with your corp!

## 🎮 EVE Online Context

**zKillboard:** The community killmail archive and statistics site for EVE Online
- Official: [zkillboard.com](https://zkillboard.com)
- API Docs: [zkillboard.com/api/](https://zkillboard.com/api/)

**Gate Camping:** A PvP tactic where fleets camp stargate jumpgates to catch targets
- Requires fleet coordination
- Generates frequent smaller kills
- This tool helps split loot quickly between operations

## ❓ FAQ

**Q: Is this a scam? Will you steal my ISK?**
A: No. This tool runs entirely in your browser. No data is stored on any server. Your ISK is never touched—you manually transfer it based on the calculator output.

**Q: Does this work offline?**
A: Yes, but you won't be able to fetch killmail data from zkillboard without internet. Manual entry works fine offline.

**Q: Can I use this in-game?**
A: No, but you can keep it open in a second monitor or alt-tab to it. Works great on mobile for quick lookups.

**Q: How accurate is the ISK calculation?**
A: As accurate as zkillboard's API. Prices are based on the last known transaction value. Market prices change constantly, so values are approximate.

**Q: Can I export to Excel?**
A: The export is a plain text file. Open it in Excel and use "Text to Columns" to split data, or copy/paste the numbers manually.

**Q: What about loot that didn't drop?**
A: The calculator only counts loot that actually dropped. Destroyed loot isn't included in zkillboard data.

## 📞 Support

- **Issues:** [GitHub Issues](https://github.com/yourusername/zkillboard-loot-tracker/issues)
- **Suggestions:** Open an issue with "Enhancement" label
- **Questions:** Check existing issues or ask in EVE Online communities

## 🙏 Credits

- **zKillboard** - For the public API and killmail data
- **CCP Games** - For EVE Online and the universe we're shooting in
- **Contributors** - Everyone who's helped improve this tool

## 📜 Changelog

### v2.0 (Latest)
- ✨ Added Losses tracking
- ✨ Added Loot breakdown with bar charts
- ✨ Added Pilot roster management
- ✨ Added Manual kill entry
- ✨ Added Session saver and history
- ✨ Added Tax calculator
- ✨ Added ISK/hour efficiency tracker
- 🎨 Redesigned UI to match zkillboard aesthetic
- 🐛 Fixed various edge cases

### v1.0
- Initial release with basic kill tracking and ISK split

## 🔮 Future Roadmap

- [ ] Persistent storage between sessions
- [ ] Character portrait images
- [ ] Alliance/Corporation integration
- [ ] Time-based analytics
- [ ] Mobile app
- [ ] Dark theme (currently only dark red)
- [ ] Real-time crew tracking

---

**Made for EVE Online pilots. Fly safe. 🚀⚔**

Questions? Ideas? Found a bug? Open an issue or submit a PR!

