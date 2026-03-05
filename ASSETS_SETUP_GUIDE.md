# 🎨 Assets Setup Guide - Logos, Music & Graphics

Your Bingo game now has slots for:
- **Organizer Logo**
- **AlphaSight HK Logo** (Sponsor)
- **Background Music**
- **Decorative Images**
- **Background Image**

---

## 📁 Folder Structure Created

```
Monthly-reconciliation/
├── assets/
│   ├── logos/          ← Put your logo files here
│   ├── music/          ← Put background music here
│   └── images/         ← Put decorative images here
├── bingo_game.html
└── ASSETS_SETUP_GUIDE.md (this file)
```

---

## 🎯 Step-by-Step Setup

### 1. Add Your Logos

#### **Option A: From Your AlphaSight Social Media Project**

You already have logos there! Let me copy them:

**Run this in PowerShell:**
```powershell
# Copy logos from AlphaSight project
Copy-Item "C:\Users\acheu\OneDrive\文件\AlphaSight Social Media\assets\logo-red.png" "C:\Users\acheu\OneDrive\文件\Monthly-reconciliation\assets\logos\alphasight-logo.png"
```

#### **Option B: Manual Copy**

1. **AlphaSight HK Logo:**
   - File: `alphasight-logo.png`
   - Location: `assets/logos/alphasight-logo.png`
   - Recommended size: 400x200px, transparent background (PNG)
   - Shows on the right side of header

2. **Organizer Logo:**
   - File: `organizer-logo.png`
   - Location: `assets/logos/organizer-logo.png`
   - Recommended size: 400x200px, transparent background (PNG)
   - Shows on the left side of header

**To add:**
1. Export your logos from Canva as PNG with transparent background
2. Rename them exactly as shown above
3. Paste into `assets/logos/` folder
4. Refresh the game!

---

### 2. Add Background Music 🎵

#### **Where to Get Free Royalty-Free Music:**

**Best Sources:**
1. **YouTube Audio Library** (Free, no attribution required)
   - https://studio.youtube.com/channel/UC.../music
   - Search: "upbeat happy music" or "game show music"
   - Download as MP3

2. **Pixabay Music** (Free, no attribution)
   - https://pixabay.com/music/
   - Search: "party music", "game show", "happy upbeat"

3. **Free Music Archive**
   - https://freemusicarchive.org/
   - Filter: "Commercial use allowed"

4. **Bensound** (Free with attribution)
   - https://www.bensound.com/
   - Try: "Funny Song", "Ukulele", "Happy Rock"

#### **Recommended Music Styles:**
- Upbeat, happy background music
- Game show style music
- Party atmosphere music
- 2-3 minutes long (it loops automatically)

#### **How to Add:**

1. Download your chosen music as **MP3**
2. Rename it to: `bingo-background.mp3`
3. Save to: `assets/music/bingo-background.mp3`
4. (Optional) Also save an OGG version for better compatibility

**File specs:**
- Format: MP3 or OGG
- Bitrate: 128kbps or higher
- Duration: 2-5 minutes (it loops)
- Volume: Normalize to -3dB to -6dB (not too loud)

---

### 3. Add Decorative Images 🎨

#### **Background Image:**

**File:** `assets/images/background.jpg`
**Purpose:** Shows behind everything with 30% opacity
**Recommended:** 
- Hong Kong skyline
- Festive party background
- Abstract colorful patterns
- Bingo ball patterns

**Where to get:**
1. **Unsplash** - https://unsplash.com/
   - Search: "hong kong skyline", "party confetti", "colorful abstract"
   - Free to use, no attribution required

2. **Pexels** - https://www.pexels.com/
   - Search: "celebration background", "festive lights"

3. **Canva**
   - Create your own 1920x1080px background
   - Export as JPG

**To add:**
1. Download/create background image
2. Rename to: `background.jpg`
3. Save to: `assets/images/background.jpg`

---

#### **Decorative Elements (Optional):**

**Files:**
- `assets/images/decoration1.png`
- `assets/images/decoration2.png`

**Purpose:** Floating animated elements in the corners
**Recommended:**
- Bingo ball graphics
- Star/sparkle effects
- Festival decorations
- Dice, casino chips

**Where to get:**
1. **PNG images with transparent background**
2. Create in Canva (200x200px)
3. Download from: https://www.flaticon.com/ (free with attribution)
4. Use emojis converted to PNG: https://emoji.gg/

**To add:**
1. Create/download PNG images (transparent background)
2. Size: 150x150px to 200x200px
3. Save as: `decoration1.png` and `decoration2.png`
4. Location: `assets/images/`

---

## 🎨 Design with Canva

### **Creating Logos in Canva:**

1. **Go to Canva** - https://www.canva.com/
2. Create custom size: **400px × 200px**
3. Design your logo/text
4. **Download as PNG** with transparent background
5. Save to `assets/logos/`

### **Creating Background:**

1. Create custom size: **1920px × 1080px**
2. Add festive/party elements, gradients, patterns
3. Download as JPG or PNG
4. Save to `assets/images/background.jpg`

### **Creating Decorations:**

1. Create custom size: **200px × 200px**
2. Design bingo balls, stars, or fun icons
3. Download as PNG with transparent background
4. Save to `assets/images/decoration1.png` and `decoration2.png`

---

## 🚀 Quick Start Checklist

### Minimum Setup (3 files):
- [ ] `assets/logos/alphasight-logo.png` (Your company logo)
- [ ] `assets/logos/organizer-logo.png` (Event organizer logo)
- [ ] `assets/music/bingo-background.mp3` (Background music)

### Full Setup (6 files):
- [ ] `assets/logos/alphasight-logo.png`
- [ ] `assets/logos/organizer-logo.png`
- [ ] `assets/music/bingo-background.mp3`
- [ ] `assets/images/background.jpg`
- [ ] `assets/images/decoration1.png`
- [ ] `assets/images/decoration2.png`

**Note:** The game works even without these files! Missing logos/images simply won't show. The game will still be playable and beautiful.

---

## 🎮 Using the Music Player

Once you add music:

1. **Play Music** - Click "播放音樂" button in the header
2. **Adjust Volume** - Use the slider (🔊)
3. **Pause Music** - Click button again (becomes "停止音樂")

The music loops automatically and plays in the background while calling numbers!

---

## 🔧 Advanced Customization

### Change Background Opacity

Open `bingo_game.html` and find (around line 30):
```css
body::before {
    ...
    opacity: 0.3;  /* Change this: 0.1 = faint, 0.5 = strong */
}
```

### Change Logo Sizes

Find (around line 60):
```css
.logo-organizer {
    height: 70px;  /* Make bigger/smaller */
}

.logo-sponsor {
    height: 55px;  /* Make bigger/smaller */
}
```

### Change Decoration Positions

Find (around line 50):
```css
.decoration-1 {
    top: 10%;    /* Change vertical position */
    left: 5%;    /* Change horizontal position */
    width: 150px; /* Change size */
}
```

### Add More Decorative Elements

Copy the `.decoration-1` CSS, rename to `.decoration-3`, change positions, and add to HTML:
```html
<div class="floating-decoration decoration-3"></div>
```

---

## 📋 Quick Copy Commands

### Copy AlphaSight Logo from Social Media Project:
```powershell
Copy-Item "C:\Users\acheu\OneDrive\文件\AlphaSight Social Media\assets\logo-red.png" "C:\Users\acheu\OneDrive\文件\Monthly-reconciliation\assets\logos\alphasight-logo.png"
```

### Open Assets Folders:
```powershell
# Open logos folder
explorer "C:\Users\acheu\OneDrive\文件\Monthly-reconciliation\assets\logos"

# Open music folder
explorer "C:\Users\acheu\OneDrive\文件\Monthly-reconciliation\assets\music"

# Open images folder
explorer "C:\Users\acheu\OneDrive\文件\Monthly-reconciliation\assets\images"
```

---

## 🎯 Recommended Free Resources Summary

| Asset Type | Source | URL |
|------------|--------|-----|
| Music | YouTube Audio Library | https://studio.youtube.com |
| Music | Pixabay Music | https://pixabay.com/music/ |
| Background Images | Unsplash | https://unsplash.com |
| Background Images | Pexels | https://www.pexels.com |
| Icons/Decorations | Flaticon | https://www.flaticon.com |
| Custom Graphics | Canva | https://www.canva.com |

---

## ❓ Troubleshooting

### Logo doesn't show:
- Check file name matches exactly (case-sensitive on some systems)
- Make sure it's PNG format
- Check it's in the right folder: `assets/logos/`
- Refresh browser (Ctrl + F5)

### Music doesn't play:
- Check file name: `bingo-background.mp3`
- Check file is in: `assets/music/`
- Click the music button (browsers block autoplay)
- Try MP3 format if OGG doesn't work

### Background image doesn't show:
- Check file name: `background.jpg` (or `.png`)
- Update the CSS if using PNG instead of JPG
- Check file is in: `assets/images/`

---

## 🎨 Next Steps

1. **Add your logos first** (most important for branding)
2. **Find and add background music** (enhances the experience)
3. **Optional: Add background image** (makes it more vibrant)
4. **Optional: Add decorations** (extra polish)

**The game is fully functional without any assets**, but they make it look professional and branded for your event!

**Need help? Let me know what you need!** 🚀
