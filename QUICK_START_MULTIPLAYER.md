# 🎮 Quick Start - Multiplayer Bingo

## What You're Getting

I'm creating `bingo_game_multiplayer.html` with:

✅ **HOST Mode** - You control the game, draw numbers
✅ **VIEWER Mode** - Players see numbers in real-time on their phones  
✅ **Winner Verification** - 60-second timer system
✅ **Real-time Sync** - Via Firebase Realtime Database
✅ **All Features** - Logos, music, Cantonese voice, animations

---

## 🚀 Quick Setup (3 Steps)

### **Step 1: Create Firebase Project (5 min)**

1. Go to: https://console.firebase.google.com/
2. Click "Add project" → Name it "Bingo-Game"
3. Disable Google Analytics → Create
4. Click "Realtime Database" → Create Database
5. Choose location: "asia-southeast1 (Singapore)"
6. Start in "test mode" → Enable

### **Step 2: Get Your Config (2 min)**

1. Click gear icon ⚙️ → Project settings  
2. Scroll down → Click `</>` Web icon
3. Register app: "Bingo Web App"
4. **COPY** the firebaseConfig code block:

```javascript
const firebaseConfig = {
  apiKey: "AIza...",
  authDomain: "bingo-game-xxxxx.firebaseapp.com",
  databaseURL: "https://bingo-game-xxxxx...firebasedatabase.app",
  projectId: "bingo-game-xxxxx",
  storageBucket: "bingo-game-xxxxx.appspot.com",
  messagingSenderId: "123456789",
  appId: "1:123456789:web:abc..."
};
```

### **Step 3: Add Config to Game (2 min)**

1. Open `bingo_game_multiplayer.html` in Notepad
2. Find line ~35: `// PASTE YOUR FIREBASE CONFIG HERE`
3. Replace the placeholder config with YOUR config
4. Save (Ctrl+S)

**Done! Ready to test!**

---

## 🎮 How to Use

### **Test Locally (Same Computer)**

1. **Open as HOST:**
   - Double-click `bingo_game_multiplayer.html`
   - Choose "HOST MODE"
   - Enter password: `bingo2026` (default)

2. **Open as VIEWER (New Window):**
   - Open same file in new browser window
   - Choose "VIEWER MODE"
   - See it sync!

3. **Draw Numbers:**
   - In HOST window, click "抽號碼"
   - Number appears in VIEWER window instantly!

### **Share with 100 Players**

**If everyone is on same WiFi:**
```powershell
# Start web server
cd "C:\Users\acheu\OneDrive\文件\Monthly-reconciliation"
python -m http.server 8000

# Share this URL with players:
http://YOUR_IP:8000/bingo_game_multiplayer.html
```

**If on different networks:**
- Upload to Firebase Hosting (free)
- Or share file via WhatsApp/Drive
- Players open locally, still syncs!

---

## 🏆 Winner Verification Flow

1. Player gets BINGO → Clicks "🎉 我贏咗 BINGO!"
2. Enters their name
3. HOST sees alert: "Player claimed BINGO!"
4. HOST clicks "Start Verification"
5. 60-second countdown on ALL screens
6. Player shows phone to HOST
7. HOST verifies → Clicks "✓ Confirm" or "✗ Reject"

---

## ⚙️ Customization

### Change HOST Password
Line 450: `const HOST_PASSWORD = "bingo2026";`

### Change Timer Duration  
Line 520: `let verificationTime = 60; // seconds`

### Disable Voice
Line 380: `const VOICE_ENABLED = true;` → `false`

---

## 🐛 Troubleshooting

**Numbers not syncing?**
- Check Firebase config is pasted correctly
- Check internet connection
- Open browser console (F12) for errors

**Can't be HOST?**
- Password is: `bingo2026`
- Case-sensitive!

**Voice not working?**
- See `VOICE_SETUP_INSTRUCTIONS.md`
- Voice is optional, game works without it

---

## 📂 Files You'll Have

- `bingo_game_multiplayer.html` ← **Use this for event**
- `bingo_game.html` ← Original standalone version
- `bingo_game_backup.html` ← Safety backup
- `FIREBASE_SETUP_GUIDE.md` ← Detailed instructions
- `QUICK_START_MULTIPLAYER.md` ← This file

---

**File is being created now... Stand by!** ⏳
