# Setup Guide — Getting Team Trip IQ on GitHub Pages

Follow these steps to get your own live copy of Team Trip IQ running in about 5 minutes.

---

## Step 1 — Create a GitHub account

If you don't have one: [github.com/signup](https://github.com/signup)

---

## Step 2 — Create a new repository

1. Go to [github.com/new](https://github.com/new)
2. **Repository name:** `TeamTripIQ` (or anything you want)
3. Set to **Public** ← required for free GitHub Pages
4. Leave everything else at defaults
5. Click **Create repository**

---

## Step 3 — Upload the files

GitHub's drag-and-drop uploader works great on iPhone and desktop.

1. On your new repo page, click **uploading an existing file** (or the **Add file** button)
2. Drag and drop all files from this folder:
   - `index.html` ← the app itself
   - `README.md`
   - `.nojekyll`
3. Scroll down, click **Commit changes**

> **Note:** `.gitignore` and the `.github/` folder are optional but recommended. GitHub may not show dotfiles in the drag interface — you can add them later.

---

## Step 4 — Enable GitHub Pages

1. Go to your repo → **Settings** tab
2. Click **Pages** in the left sidebar
3. Under **Source**, select **Deploy from a branch**
4. Branch: `main` | Folder: `/ (root)`
5. Click **Save**

GitHub will show a banner: *"Your site is being published..."*

---

## Step 5 — Get your URL

After ~60 seconds, your app is live at:

```
https://[your-github-username].github.io/TeamTripIQ
```

Bookmark it, share it with parents, and add it to your iPhone home screen.

---

## Adding to iPhone Home Screen

1. Open the URL in Safari (not Chrome)
2. Tap the **Share** button (box with arrow)
3. Scroll down → **Add to Home Screen**
4. Name it "Trip IQ" → tap **Add**

It will appear as an icon and open full-screen like a native app.

---

## Updating the App

When there's a new version of `index.html`:

1. Go to your repo on GitHub
2. Click on `index.html`
3. Click the **pencil icon** (Edit) or drag-and-drop a new file
4. GitHub will ask you to commit — click **Commit changes**
5. The live site updates within ~30 seconds

---

## Sharing with Parents

Send parents the URL: `https://[username].github.io/TeamTripIQ`

Each parent needs their **4-digit PIN** which you set in the app under:
> Edit mode → Roster → tap a player → Edit → Login PIN

**Admin PIN is `0000`** — keep this to yourself.

---

## Backing Up Your Data

All data lives in each user's browser (`localStorage`). To back up:

1. Open the app in Chrome on desktop
2. Press `F12` → **Application** tab → **Local Storage**
3. Find the key `tripiq4` → right-click → Copy value
4. Paste into a text file and save

To restore: paste the value back into the same localStorage key.

A simpler option: use **Roster → ⬇️ Export CSV** before each trip.

---

## Troubleshooting

| Problem | Fix |
|---------|-----|
| Site shows 404 | Wait 2 minutes after enabling Pages, then hard-refresh |
| App resets to default data | localStorage was cleared — re-enter data or restore from backup |
| PIN doesn't work | Admin is `0000`. Parent PINs are set in Roster → Edit |
| Keypad doesn't appear | Try a different browser; Safari on iPhone works best |
| Google Sheets import fails | Make sure sheet is published as CSV (not HTML) and the URL ends in `?output=csv` |
