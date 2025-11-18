# Quick Test Guide

## How to Test the Implementation

### 1. Background Music File

The background music file is already included in the repository at:
`game/assets/children-music-loop-creative-fun-262427.mp3`

### 2. Test the Game

**Option A: Local File System**
```bash
# Simply open the file in your browser:
open game/index.html
# or
firefox game/index.html
# or
chrome game/index.html
```

**Option B: Local Server (Recommended)**
```bash
cd game
python3 -m http.server 8080
# Then visit: http://localhost:8080
```

### 3. Test Focus Handling

Once the game is running with the music file:

1. **Test Tab Switching:**
   - Open the game
   - Music should be playing
   - Switch to another tab
   - Music should pause
   - Switch back to the game tab
   - Music should resume

2. **Test App Switching:**
   - Open the game
   - Music should be playing
   - Switch to another application (Alt+Tab or Cmd+Tab)
   - Music should pause
   - Switch back to the browser
   - Music should resume

3. **Test Game Over:**
   - Play until game over
   - Music should fade out
   - Click "Restart"
   - Music should start playing again

### 4. Test Without Music File

To verify error handling works:
```bash
# Temporarily rename the music file
mv game/assets/children-music-loop-creative-fun-262427.mp3 game/assets/children-music-loop-creative-fun-262427.mp3.bak

# Open the game - it should still work
# Check browser console for warning message
# Sound effects should still play

# Restore the file
mv game/assets/children-music-loop-creative-fun-262427.mp3.bak game/assets/children-music-loop-creative-fun-262427.mp3
```

### Expected Behavior

✅ **With music file:**
- Background music plays on game start (may require user interaction due to browser autoplay policies)
- Music loops continuously
- Music pauses when focus is lost (tab/app switch)
- Music resumes when focus is gained
- Music fades out on game over
- Sound effects continue to work

✅ **Without music file:**
- Game loads and works normally
- Sound effects still play
- Console shows warning: "Background music could not be loaded. Please check assets/README.md for download instructions."
- No errors or crashes

### Browser Console Messages

Look for these messages to verify everything is working:

```
✓ Normal operation: No errors
✓ Music file missing: "Background music could not be loaded..."
✓ Autoplay prevented: "Autoplay was prevented. User interaction required."
```

### Troubleshooting

**Music doesn't play:**
- Check if file exists at `game/assets/children-music-loop-creative-fun-262427.mp3`
- Check browser console for errors
- Try clicking on the game (autoplay may require user interaction)
- Check browser's autoplay settings

**Music doesn't pause/resume:**
- Check browser console for errors
- Try in a different browser (some browsers handle visibility differently)
- Make sure you're using a modern browser (Chrome, Firefox, Safari, Edge)

**Sound effects don't play:**
- This is a separate issue (not related to this PR)
- Sound effects use Web Audio API, which always works
