# 🔊 Cantonese Voice Setup Instructions
# 粵語語音設置說明

## Quick Start (5 minutes)

Your Bingo game is ready! To enable **perfect natural Cantonese voice**, follow these steps:

---

## Step 1: Get Google Cloud API Key

### 1.1 Create Google Cloud Account
- Go to: **https://console.cloud.google.com/**
- Sign in with your Google account
- Accept terms and create account (if first time)

### 1.2 Create a New Project
- Click "Select a project" dropdown at the top
- Click "NEW PROJECT"
- Name it: `Bingo Game` (or any name you like)
- Click "CREATE"
- Wait ~30 seconds for project creation

### 1.3 Enable Text-to-Speech API
- In the top search bar, type: `Text-to-Speech API`
- Click on "Cloud Text-to-Speech API"
- Click the blue "ENABLE" button
- Wait for it to enable (~30 seconds)

### 1.4 Create API Key
- In the left menu, go to: **APIs & Services → Credentials**
- Click "+ CREATE CREDENTIALS" at the top
- Select "API key"
- Your API key will appear! Copy it immediately
- (Optional but recommended) Click "RESTRICT KEY" and limit to "Cloud Text-to-Speech API"

**Your API key looks like:** `AIzaSyD1234567890abcdefghijklmnopqrstuvwxyz`

---

## Step 2: Add API Key to Your Game

### 2.1 Open the Game File
- Open file: `bingo_game.html` in a text editor (Notepad, VS Code, etc.)

### 2.2 Find This Line (around line 308)
```javascript
const GOOGLE_TTS_API_KEY = 'YOUR_API_KEY_HERE';
```

### 2.3 Replace with Your Key
```javascript
const GOOGLE_TTS_API_KEY = 'AIzaSyD1234567890abcdefghijklmnopqrstuvwxyz';
```
*(Use YOUR actual key from Step 1.4)*

### 2.4 Save the File
- Press `Ctrl + S` to save
- Close the text editor

---

## Step 3: Test the Voice!

### 3.1 Open the Game
- Double-click `bingo_game.html` to open in browser
- Or refresh if already open

### 3.2 Check Status
- Look at the bottom of the control panel
- Should say: **"✓ 已啟用 Enabled (粵語)"** in green

### 3.3 Draw a Number
- Click "🎱 抽號碼 Draw Number"
- You should hear: Natural Cantonese voice saying the number!
- Example: Number 5 → "五" spoken aloud

---

## 🎭 Change Voice (Optional)

You can choose different voices!

**Available Cantonese Voices:**
- `yue-HK-Standard-A` - Female (Default) ⭐
- `yue-HK-Standard-B` - Male
- `yue-HK-Standard-C` - Female (Alternative)
- `yue-HK-Standard-D` - Male (Alternative)

**To Change:**
1. Open `bingo_game.html` in text editor
2. Find function `speakCantonese()` (around line 380)
3. Change this line:
```javascript
name: 'yue-HK-Standard-A', // Change to B, C, or D
```
4. Save and refresh browser

---

## 💰 Pricing

**FREE Tier:**
- 1,000,000 characters per month FREE
- Each number = ~2-4 characters
- That's **~300,000+ numbers per month FREE!**

**After Free Tier:**
- $4 USD per 1 million characters
- For a hobby game, you'll likely never pay anything

---

## 🐛 Troubleshooting

### Problem: Voice Status shows "❌ 需要配置 API Key"
**Solution:** API key not added correctly
- Check Step 2.2 - make sure you replaced the entire text between quotes
- Save the file and refresh browser

### Problem: Voice Status shows "✓ Enabled" but no sound
**Solution:** Browser permissions
- Click the 🔒 lock icon in browser address bar
- Allow "Sound" permissions
- Refresh page and try again

### Problem: Error in browser console (Press F12 to see)
**Solution:** API key restrictions or billing
- Go back to Google Cloud Console
- Check if Text-to-Speech API is enabled
- Check if billing is enabled (required even for free tier)
- Remove any IP restrictions on the API key

### Problem: Sound is robotic or English
**Solution:** Wrong language code
- Check `languageCode: 'yue-HK'` is correct
- Make sure you didn't accidentally use `zh-HK` (Mandarin)

---

## 🎨 Integrate Canva Graphics (Bonus)

Want to add your custom artwork from Canva?

### For Background:
1. In Canva, design your background (1920x1080px)
2. Download as PNG
3. Save as: `background.png` (same folder as bingo_game.html)
4. In `bingo_game.html`, find `body` style (around line 13)
5. Add:
```css
background-image: url('background.png');
background-size: cover;
```

### For Bingo Balls:
1. Design custom ball graphics in Canva (200x200px circles)
2. Export as PNG files: `ball-1.png`, `ball-2.png`, etc.
3. Save in a folder called `images/`
4. Update `.bingo-cell` and `.number-ball` CSS with `background-image`

---

## 📞 Need Help?

If you get stuck:
1. Check browser console for errors (Press F12)
2. Verify API key is copied correctly (no extra spaces)
3. Make sure billing is enabled in Google Cloud (even for free tier)
4. Test with a simple draw first before auto-mode

---

## ✅ Success Checklist

- [ ] Google Cloud project created
- [ ] Text-to-Speech API enabled
- [ ] API key created and copied
- [ ] API key added to `bingo_game.html`
- [ ] File saved
- [ ] Voice status shows green "✓ 已啟用"
- [ ] Can hear natural Cantonese when drawing numbers
- [ ] Sounds amazing! 🎉

---

**Enjoy your Bingo game with perfect Cantonese voice! 恭喜你！🎊**
