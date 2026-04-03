# 🏐 Team Trip IQ

A mobile-first trip management app for youth volleyball teams. Handles everything from meal orders and parent contacts to duty assignments and supply lists — all in a single HTML file with no backend required.

**Live demo:** `https://[your-username].github.io/TeamTripIQ`

---

## Features

- **PIN-based login** — each parent/player has a 4-digit PIN; admin is `0000`
- **Personal dashboard** — parents see their child's meal orders, payment status, and assigned duties on login
- **Multi-team & multi-event** — switch between teams and trips in the header
- **Collapsible meal days** — meals grouped by date, each day collapsible
- **EZ Cater integration** — coordinator order links per meal, order count tracking (expected / entered / missing)
- **Inline attendee contacts** — parents, grandparents, spectators listed directly under each player with tap-to-call and tap-to-email
- **Duties system** — assign multiple parents to duties, unassigned duties highlighted in red
- **Budget tracking** — collected vs. estimated spend, Venmo deep-link for payment
- **Supply checklist** — categorized, renameable categories, tap to check off
- **Clone trip** — copy roster, duties, and supplies into a new event with one tap
- **Export CSV** — download full roster + attendees for Google Sheets or printing
- **Google Sheets import** — paste a published CSV URL to sync roster data
- **Persistent login** — stays logged in via localStorage across sessions
- **Fully offline** — no server, no database, no accounts

---

## Setup & Deployment

### Deploy to GitHub Pages (recommended)

1. Fork or clone this repo
2. Go to **Settings → Pages**
3. Set source to `main` branch, root `/`
4. Your app will be live at `https://[username].github.io/TeamTripIQ`

### Run locally

Just open `index.html` in any browser. No build step, no dependencies.

---

## How to Use

### First-time setup (Admin)

1. Open the app and enter PIN `0000`
2. Tap your team name in the header → add or rename teams
3. Tap the event name → edit event details, or add a new event
4. Go to **Roster** tab → add players and coaches, set their PINs
5. Add attendees (parents/spectators) under each player
6. Go to **Meals** → add meals, paste EZ Cater links, enter orders
7. Go to **Duties** → add duties and assign parents
8. Go to **Supplies** → build your Costco/Instacart list

### For parents

Share the app URL and each parent's 4-digit PIN. They log in and see:
- Their child's meal orders for the trip
- Outstanding items (unpaid fee, missing orders)
- Their assigned duties
- Event info, schedule links, hotel details

### PIN system

| Who | PIN |
|-----|-----|
| Admin / Coach | `0000` |
| Each parent/player | Set in Roster → Edit → Login PIN field |
| Default (14 Blues) | Soren Wright: `2312`, others follow `[jersey#][2-digit-index]` pattern |

---

## Data & Privacy

All data is stored in `localStorage` on the user's device. There is no server, no cloud sync, and no data leaves the browser. Clearing browser data or switching devices resets the app to defaults.

To back up data: use the **Export CSV** button on the Roster page, or copy `localStorage['tripiq4']` from browser dev tools.

---

## Google Sheets Sync

The app can import roster data from a published Google Sheet:

1. Open your Google Sheet
2. **File → Share → Publish to web**
3. Choose your sheet tab → **CSV** format → Publish
4. Copy the URL
5. In the app: Roster → 📊 Import → paste URL → Import

**Expected columns:** `Name`, `Number`, `Parents`, `Phone1`, `Phone2`, `Email`, `Allergy`, `Hotel`, `Paid` (Yes/No), `PIN`

Column matching is flexible — the app looks for partial matches (e.g. `phone` matches `Phone1`, `Phone (Cell)`, etc.).

The import adds new people and updates existing ones by name match. It never deletes anyone or removes meal orders.

---

## File Structure

```
TeamTripIQ/
├── index.html        ← The entire app (single file)
├── README.md         ← This file
├── .nojekyll         ← Tells GitHub Pages not to process with Jekyll
└── .github/
    └── CODEOWNERS    ← Optional: restrict who can push to main
```

---

## Customizing Default Data

The app ships pre-loaded with the 14 Blues (Arizona 2026) and 16 Orlando (AAU Nationals 2025) team data. To replace with your own:

1. Open `index.html` in a text editor
2. Find the `const SEED = {` block near the top of the `<script>` tag
3. Edit the `teams` array — each team has `name` and `events[]`
4. Each event has: `players[]`, `coaches[]`, `meals[]`, `duties[]`, `supplies[]`, `links[]`

Or just use the app itself in admin mode — everything is editable in-app and saved to localStorage.

---

## Built With

- Vanilla HTML / CSS / JavaScript — zero dependencies
- [Barlow Condensed](https://fonts.google.com/specimen/Barlow+Condensed) + [Barlow](https://fonts.google.com/specimen/Barlow) + [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono) via Google Fonts
- localStorage for persistence
- GitHub Pages for hosting

---

## Version History

| Version | Notes |
|---------|-------|
| v6 | Attendees per player (parents/spectators), Emergency Contact tile, Parents tab removed, PIN keypad fixed, CSV export with attendees |
| v5 | Parent contact page, email field, Google Sheets import/export |
| v4 | Multi-team support, PIN login, collapsible meal days, duties multi-assign |
| v3 | Full Orlando 2025 data, order counts, clone trip, EZ Cater links |
| v1–2 | Initial build from AZ 2026 spreadsheet |

---

## Contributing

This is a private team tool. To suggest changes, open an issue or submit a pull request. All logic lives in `index.html` — there's no build process.

---

*Built for Edison Boys Beach Volleyball — Huntington Beach, CA*
