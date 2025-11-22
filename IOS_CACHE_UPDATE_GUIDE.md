# iOS Cache Update Solution - User Guide

## Problem Solved
iOS Safari aggressively caches Progressive Web Apps (PWAs), which can prevent users from seeing updates to the game. This solution provides multiple ways to force cache updates.

## Solution Overview

### For Players

#### Method 1: Clear Cache Button (Recommended)
This is the easiest and most reliable method:

1. **Open the game menu**
   - Tap the hamburger menu icon (☰) in the top-left corner of the game

2. **Locate the Clear Cache button**
   - Scroll to the bottom of the menu
   - You'll see a purple button labeled "Clear Cache & Reload"

3. **Tap the button**
   - The button will show "Clearing..." while it works
   - The page will automatically reload with fresh content
   - You'll now see the latest version of the game

#### Method 2: Automatic Updates
The game automatically checks for updates:
- Every 60 seconds while you're playing
- When you return to the browser tab
- When you reopen the app

If an update is found, the game will automatically reload to show the new version.

#### Method 3: Browser Cache Clear (iOS Safari)
If the above methods don't work:
1. Open Settings on your iPhone/iPad
2. Scroll down and tap "Safari"
3. Tap "Clear History and Website Data"
4. Confirm by tapping "Clear History and Data"
5. Reopen the game in Safari

#### Method 4: Reinstall PWA (Home Screen App)
If you added the game to your home screen:
1. Long-press the game icon on your home screen
2. Tap "Remove App" or the "X" icon
3. Confirm deletion
4. Open Safari and navigate to the game URL
5. Tap the Share button (box with arrow)
6. Tap "Add to Home Screen"
7. The fresh version will now be installed

## Visual Guide

### Where to Find the Clear Cache Button

```
┌─────────────────────────┐
│  ☰  Score    High Score │  ← Tap the ☰ menu icon
├─────────────────────────┤
│                         │
│   🍉 Fruit Merge        │
│                         │
│   Drop and merge        │
│   identical fruits...   │
│                         │
│   ┌─────────────────┐   │
│   │     Start       │   │
│   └─────────────────┘   │
│   ┌─────────────────┐   │
│   │    Restart      │   │
│   └─────────────────┘   │
│   ┌───────┬────────┐    │
│   │Music: │Sounds: │    │
│   │  On   │  On    │    │
│   └───────┴────────┘    │
│   ┌─────────────────┐   │
│   │ Clear Cache &   │   ← This button!
│   │     Reload      │   │
│   └─────────────────┘   │
│                         │
└─────────────────────────┘
```

## For Developers

### How to Deploy Updates

1. **Make your code changes** to any game files
2. **Update the version number** in `game/sw.js`:
   ```javascript
   const VERSION = '1.0.2'; // Increment from 1.0.1
   ```
3. **Deploy all files** to your web server
4. **Users will automatically get updates**:
   - Within 60 seconds if the app is open
   - When they return to the browser tab
   - When they tap "Clear Cache & Reload"

### Version Numbering

Follow semantic versioning:
- `1.0.1` → `1.0.2`: Bug fixes or minor tweaks
- `1.0.2` → `1.1.0`: New features
- `1.1.0` → `2.0.0`: Major changes

### Testing Updates

After deploying:
1. Open the browser console (F12)
2. Look for these messages:
   - `"Opened cache: fruit-merge-v1.0.2"`
   - `"Deleting old cache: fruit-merge-v1.0.1"`
   - `"Service Worker updated to version: 1.0.2"`

## Technical Details

### How It Works

1. **Version-Based Caching**
   - Each version gets its own cache (e.g., `fruit-merge-v1.0.1`)
   - When version changes, a new cache is created
   - Old caches are automatically deleted

2. **Network-First for HTML**
   - HTML files are always fetched from the network first
   - Ensures the latest code is delivered
   - Falls back to cache if offline

3. **Cache-First for Assets**
   - Images, CSS, and JS files are served from cache
   - Faster loading after first visit
   - Updated when version changes

4. **Automatic Updates**
   - Service Worker checks for updates every 60 seconds
   - Also checks when page becomes visible
   - New service workers activate immediately via `skipWaiting()`

5. **Manual Cache Clearing**
   - "Clear Cache & Reload" button sends message to Service Worker
   - Service Worker deletes all caches
   - Page reloads automatically
   - 10-second timeout prevents hanging

## Troubleshooting

### Problem: Still seeing old version after clearing cache

**Solution:**
1. Try Method 4 (Reinstall PWA) if using home screen app
2. Close all browser tabs with the game
3. Force-quit Safari (swipe up from app switcher)
4. Reopen and try again

### Problem: "Clear Cache & Reload" button doesn't work

**Solution:**
1. Check your internet connection
2. If offline, the button won't work
3. Wait for connection and try again
4. The button has a 10-second timeout and will reload anyway

### Problem: Automatic updates not happening

**Solution:**
1. Check browser console for errors
2. Ensure service worker is registered
3. Try manual "Clear Cache & Reload"
4. Check if browser supports service workers

## Browser Compatibility

✅ **Supported Browsers:**
- iOS Safari 11.3+
- Chrome (all platforms)
- Firefox
- Edge
- Samsung Internet

⚠️ **Limited Support:**
- Older browsers without Service Worker support
- Private/Incognito mode (limited caching)

## Additional Resources

- See `CACHE_UPDATE_TEST.md` for detailed testing procedures
- See `README.md` for general game information
- Check browser console for debugging information
