# Setup Instructions

## Background Music Setup

Due to network restrictions in the development environment, the background music file needs to be manually downloaded and placed in the correct location.

### Steps to Complete Setup:

1. **Download the background music:**
   - Visit: https://pixabay.com/music/happy-childrens-tunes-children-music-loop-creative-fun-262427/
   - Click the download button to get the MP3 file
   - The file will be named something like `children-music-loop-creative-fun-262427.mp3`

2. **Place the file in the correct location:**
   - Rename the downloaded file to `background-music.mp3`
   - Place it in the `game/assets/` directory
   - Final path should be: `game/assets/background-music.mp3`

3. **Verify the setup:**
   - Open `game/index.html` in a web browser
   - The background music should start playing automatically (browser may require user interaction first)
   - When you switch tabs or apps, the music should pause
   - When you return to the game tab, the music should resume

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
