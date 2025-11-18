# merge_game
An AI generated game

## Sound Effects and Music Attribution

### Sound Effects
Sound effects (drop and merge sounds) are generated programmatically using the Web Audio API. These are original works created specifically for this game and are in the **public domain**.

### Background Music
Background music is sourced from Pixabay:
- **Track:** Children Music Loop Creative Fun
- **Source:** https://pixabay.com/music/happy-childrens-tunes-children-music-loop-creative-fun-262427/
- **License:** Pixabay License - Free for commercial and non-commercial use

To set up the background music:
1. Download the MP3 file from the link above
2. Save it as `game/assets/background-music.mp3`

### Audio Features
- **Drop Sound**: A descending tone played when fruits are released
- **Merge Sound**: A cheerful ascending chime played when fruits merge
- **Background Music**: A continuous looping melody during gameplay that fades out when the game is paused or ended
- **Focus Handling**: Music automatically pauses when you switch tabs or apps, and resumes when you return to the game
