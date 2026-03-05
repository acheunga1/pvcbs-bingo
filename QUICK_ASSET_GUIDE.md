# 🎬 Quick Asset Upload Guide

## 📍 Folder Locations

### Assets folder:
```
C:\Users\acheu\OneDrive\文件\Monthly-reconciliation\assets\
```

### Subfolders:
- **logos/** - For company/sponsor logos
- **music/** - For background music
- **images/** - For background images/videos and decorations

---

## 🎵 How to Add Music

### Step 1: Download Music
- **YouTube Audio Library**: https://studio.youtube.com → Audio Library
- **Pixabay**: https://pixabay.com/music/
- Search: "upbeat happy music", "game show music", "party music"

### Step 2: Add to Game
1. Download as **MP3** format
2. **Drag & drop** into: `assets/music/` folder
3. **Rename to:** `bingo-background.mp3`
4. Refresh browser - Done!

**No upload needed** - it's a local file!

---

## 🎨 Template Dimensions

| Asset | Size | Format | Location |
|-------|------|--------|----------|
| **Organizer Logo** | 400×200px | PNG transparent | `assets/logos/organizer-logo.png` |
| **AlphaSight Logo** | 400×200px | PNG transparent | `assets/logos/alphasight-logo.png` ✓ |
| **Background Image** | 1920×1080px | JPG or PNG | `assets/images/background.jpg` |
| **Background Video** | 1920×1080px | MP4 | `assets/images/background.mp4` |
| **Decoration 1** | 200×200px | PNG transparent | `assets/images/decoration1.png` |
| **Decoration 2** | 200×200px | PNG transparent | `assets/images/decoration2.png` |
| **Music** | 2-5 minutes | MP3 (128kbps+) | `assets/music/bingo-background.mp3` |

---

## 🎬 **YES! MP4 Video Backgrounds Supported!**

### How to Add MP4 Background:

1. **Get a video:**
   - Download from Pexels: https://www.pexels.com/videos/
   - Search: "confetti falling", "party lights", "bokeh background"
   - Or create in Canva (animated background)

2. **Prepare the video:**
   - **Resolution:** 1920×1080px (Full HD)
   - **Duration:** 10-30 seconds (it loops)
   - **Format:** MP4
   - **Size:** Keep under 10MB for smooth playback

3. **Add to game:**
   - Save as: `background.mp4`
   - Move to: `assets/images/background.mp4`
   - Refresh browser

**The video will:**
- Play automatically in the background
- Loop continuously
- Show at 30% opacity (subtle effect)
- Won't interfere with gameplay

### Video vs Image:
- **Video** = More dynamic, eye-catching (uses more resources)
- **Image** = Static, faster loading (fallback if no video)
- You can have **both** - video plays if exists, otherwise image shows

---

## 🚀 Quick Setup Steps

### Minimum (3 files):
1. Add organizer logo: `organizer-logo.png` → `assets/logos/`
2. Add music: `bingo-background.mp3` → `assets/music/`
3. Done! (AlphaSight logo already added ✓)

### Full Setup (add any/all):
- **Logos** (2 files) → `assets/logos/`
- **Music** (1 file) → `assets/music/`
- **Background** (image OR video) → `assets/images/`
- **Decorations** (optional, 2 files) → `assets/images/`

---

## 📁 How to Access Folders Quickly

**PowerShell commands:**
```powershell
# Open logos folder
explorer "C:\Users\acheu\OneDrive\文件\Monthly-reconciliation\assets\logos"

# Open music folder
explorer "C:\Users\acheu\OneDrive\文件\Monthly-reconciliation\assets\music"

# Open images folder
explorer "C:\Users\acheu\OneDrive\文件\Monthly-reconciliation\assets\images"
```

**Or** navigate manually:
```
OneDrive → 文件 → Monthly-reconciliation → assets
```

---

## 🎥 Best Free Video Sources

### Pexels Videos (Best!)
- URL: https://www.pexels.com/videos/
- Search terms:
  - "confetti falling"
  - "party celebration"
  - "bokeh lights"
  - "abstract colorful"
  - "hong kong night"
- Download: **Free License** (no attribution needed)

### Pixabay Videos
- URL: https://pixabay.com/videos/
- Similar search terms
- All free, no attribution

### Canva (Create Your Own)
1. Create **1920×1080px** design
2. Add animations
3. Download as MP4 video

---

## 💡 Pro Tips

### For Music:
- Choose **upbeat/happy** music (not too intense)
- **2-3 minutes** is perfect (it loops)
- Volume normalized to **-6dB** (not too loud)
- Test volume in the game (use slider)

### For Videos:
- **Keep it subtle** - 30% opacity already set
- **Shorter is better** - 10-20 seconds (smaller file, smooth loop)
- **Avoid busy/distracting videos** - simple motion works best
- **Test file size** - under 10MB recommended

### For Logos:
- **PNG with transparent background**
- **High resolution** (will scale down smoothly)
- **Clear, readable** at smaller sizes

---

## ❓ FAQ

**Q: Do I need ALL the files?**
A: No! The game works without any. They just enhance the experience.

**Q: Can I use different file names?**
A: Yes, but you need to update the HTML code. Easiest to use the exact names listed.

**Q: Will video slow down the game?**
A: Not if under 10MB. Modern browsers handle it well.

**Q: Can I use both image AND video?**
A: Yes! Video plays if it exists, image is fallback.

**Q: What if music doesn't play?**
A: Click the "播放音樂" button - browsers block autoplay.

**Q: Can I change opacity/volume?**
A: Yes! See ASSETS_SETUP_GUIDE.md for customization.

---

## ✅ Current Status

- ✓ **Folders created**
- ✓ **AlphaSight logo** added
- ⏳ **Organizer logo** - add your logo file
- ⏳ **Background music** - add MP3 file
- ⏳ **Background** - add JPG/PNG or MP4 video
- ⏳ **Decorations** - optional PNG files

---

**No complicated upload process - just drag & drop files into folders!** 🎯
