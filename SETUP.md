# Setup Instructions

## Background Music Setup

The background music file has been uploaded to the repository.

### File Location:

- **Path:** `game/assets/children-music-loop-creative-fun-262427.mp3`
- **Source:** https://pixabay.com/music/happy-childrens-tunes-children-music-loop-creative-fun-262427/
- **License:** Pixabay License - Free for commercial and non-commercial use

### Verify the setup:

1. Open `game/index.html` in a web browser
2. The background music should start playing automatically (browser may require user interaction first)
3. When you switch tabs or apps, the music should pause
4. When you return to the game tab, the music should resume

## Features Implemented

### 1. Background Music from Pixabay
- Replaced the programmatically generated background music with a real audio file
- The music loops continuously during gameplay
- Fades out gracefully when the game ends or is restarted

### 2. Focus Handling
- Music automatically pauses when you switch to another tab (Page Visibility API)
- Music automatically pauses when you switch to another app (window blur event)
- Music automatically resumes when you return to the game (Page Visibility API + window focus event)
- Prevents music from playing in the background when you're not using the game

### 3. Error Handling
- If the music file is not found, the game will still work (sound effects continue)
- A console warning will be shown with instructions to download the file
- Graceful fallback for browsers that don't support autoplay

## Technical Details

- Sound effects (drop and merge sounds) remain generated via Web Audio API
- Background music uses HTML5 Audio element for better file support
- Page Visibility API handles tab switching
- Window focus/blur events handle app switching
- Volume fades out smoothly when stopping music
