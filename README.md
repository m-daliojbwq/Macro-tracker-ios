# Macro Tracker PWA - Setup Guide

## What's Included
- `index.html` — The full app (tracker + AI food scanner)
- `manifest.json` — PWA configuration
- `sw.js` — Service worker for offline support
- `icon-192.png` / `icon-512.png` — App icons

## How to Install on Your Android Phone

### Option 1: GitHub Pages (Recommended — Free, 2 minutes)

1. **Create a GitHub account** at github.com (if you don't have one)
2. **Create a new repository**:
   - Go to github.com → click "+" → "New repository"
   - Name it `macro-tracker`
   - Set it to **Public**
   - Click "Create repository"
3. **Upload the files**:
   - Click "uploading an existing file"
   - Drag all 5 files into the upload area
   - Click "Commit changes"
4. **Enable GitHub Pages**:
   - Go to Settings → Pages
   - Under "Source", select **main** branch
   - Click Save
   - Your app will be live at: `https://yourusername.github.io/macro-tracker/`
5. **Install on your phone**:
   - Open that URL in Chrome on your Android
   - Tap the **3-dot menu** (⋮) → **"Add to Home Screen"** or **"Install app"**
   - It now works like a native app!

### Option 2: Netlify Drop (Easiest — 30 seconds)

1. Go to **app.netlify.com/drop** in your browser
2. Drag the entire `macro-pwa` folder onto the page
3. Netlify gives you a URL instantly
4. Open that URL on your Android phone in Chrome
5. Tap ⋮ → **"Add to Home Screen"**

### Option 3: Local Testing

1. Install a simple server: `npx serve .` (requires Node.js)
2. Open the local URL on your phone (must be on same WiFi)
3. Note: Camera/install features require HTTPS, so this is for testing only

## Setting Up the AI Food Scanner

The scanner needs an Anthropic API key to work standalone:

1. Go to **console.anthropic.com**
2. Sign up or log in
3. Go to **API Keys** → **Create Key**
4. Copy the key (starts with `sk-ant-...`)
5. Open the app → tap **⚙️** (settings gear in the header)
6. Paste your key → tap **Save Key**

**Pricing:** Scanning a photo costs roughly $0.003–0.01 per scan (fractions of a penny).
At 5 scans/day, that's about $1-1.50/month — much cheaper than any subscription app.

Your key is stored locally on your device only. It's never sent anywhere except
directly to Anthropic's API when you scan food.

## Features
- 📸 AI food scanner (photos of meals OR nutrition labels)
- 📊 Calorie & macro tracking (1,600 cal / 190P / 90C / 53F)
- 🍗 16 common foods pre-loaded for quick logging
- ✏️ Custom food entry
- 🍽️ Meal categorization (Breakfast/Lunch/Dinner/Snack)
- 💾 Data persists in localStorage (auto-resets daily)
- 📱 Installable as an Android app via PWA
- 🔄 Works offline (except AI scanning which needs internet)

## Notes
- Data resets each day automatically.
- All data stays on your device — nothing is sent to a server.
- The AI scanner needs internet to work, but all other features work offline.
- You can customize your calorie/macro targets in the ⚙️ settings panel.
