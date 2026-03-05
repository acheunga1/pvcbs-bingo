# Bingo Game Project

## Overview
A browser-based BINGO game for PVCBS events. Single-player and multiplayer modes. Built with plain HTML/CSS/JS — no build step required.

## File Structure
```
bingo_game.html            # Main single-player game
bingo_game_multiplayer.html  # Multiplayer version (Firebase)
bingo_game_backup.html     # Backup of main game
bingo_multiplayer_template.html  # Multiplayer template
troubleshoot_voice.html    # Voice feature troubleshooting page
assets/                    # Logos and media (PVCBS branding)
```

## Key Features
- Cantonese/Traditional Chinese UI (zh-HK)
- Voice announcements for bingo calls
- Background video support
- Firebase multiplayer support
- Custom phrases and branding

## How to Run
Just open any `.html` file directly in a browser — no server needed for single-player.
For multiplayer, Firebase config must be set up (see FIREBASE_SETUP_GUIDE.md).

## Development Notes
- No build tools, no npm, no dependencies — pure HTML/CSS/JS
- Assets are referenced via relative path `assets/`
- Voice feature uses Web Speech API (browser built-in)
- Multiplayer uses Firebase Realtime Database
