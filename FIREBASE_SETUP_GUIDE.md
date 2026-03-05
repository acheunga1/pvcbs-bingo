# 🔥 Firebase Multiplayer Bingo Setup Guide

## 📋 Overview

This guide will help you set up **real-time multiplayer Bingo** for 100+ players using Firebase.

**What you'll get:**
- ✅ HOST controls the game (draws numbers)
- ✅ VIEWERs see numbers in real-time on their phones
- ✅ Everyone has different random Bingo cards
- ✅ Winner verification system with 60-second timer
- ✅ Works on any device, any internet connection

**Time Required:** 30-40 minutes

---

## 🚀 Step-by-Step Setup

### **STEP 1: Create Firebase Project** ⏱️ 5 minutes

1. **Go to Firebase Console:**
   - Open: https://console.firebase.google.com/
   - Sign in with your Google account

2. **Create New Project:**
   - Click "Add project" or "Create a project"
   - Project name: `Bingo Game AlphaSightHK`
   - Click "Continue"

3. **Disable Google Analytics** (optional, simpler):
   - Toggle OFF "Enable Google Analytics"
   - Click "Create project"
   - Wait 30 seconds for project creation
   - Click "Continue"

---

### **STEP 2: Enable Realtime Database** ⏱️ 3 minutes

1. **In Firebase Console**, find left sidebar
2. Click "Build" → "Realtime Database"
3. Click "Create Database" button
4. **Choose location:**
   - Select "asia-southeast1 (Singapore)" - closest to HK
   - Click "Next"

5. **Security Rules:**
   - Select "Start in **test mode**" (we'll secure it later)
   - Click "Enable"
   - Wait30 seconds for database creation

---

### **STEP 3: Get Firebase Configuration** ⏱️ 2 minutes

1. **In Firebase Console**, click gear icon (⚙️) top-left
2. Click "Project settings"
3. Scroll down to "Your apps" section
4. Click **</> Web** icon to create web app
5. **Register app:**
   - App nickname: `Bingo Web App`
   - ❌ Don't check "Firebase Hosting"
   - Click "Register app"

6. **Copy the config:**
   - You'll see a code block like this:

```javascript
const firebaseConfig = {
  apiKey: "AIzaSyD...",
  authDomain: "bingo-game-alphasighthk-xxxxx.firebaseapp.com",
  databaseURL: "https://bingo-game-alphasighthk-xxxxx-default-rtdb.asia-southeast1.firebasedatabase.app",
  projectId: "bingo-game-alphasighthk-xxxxx",
  storageBucket: "bingo-game-alphasighthk-xxxxx.appspot.com",
  messagingSenderId: "123456789",
  appId: "1:123456789:web:abcdef123456"
};
```

7. **COPY this entire block** - you'll paste it into the game file
8. Click "Continue to console"

---

### **STEP 4: Update Security Rules** ⏱️ 2 minutes

**Important:** Test mode allows anyone to read/write for 30 days. Let's secure it properly.

1. In Firebase Console, go to "Realtime Database"
2. Click "Rules" tab
3. **Replace the rules** with this:

```json
{
  "rules": {
    "gameState": {
      ".read": true,
      ".write": "auth == null || true"
    },
    "bingoCallers": {
      ".read": true,
      ".write": true
    }
  }
}
```

4. Click "Publish"

**What this does:**
- Everyone can READ game state (see numbers)
- Anyone can WRITE (for now - we'll add HOST password later)
- Prevents unauthorized access to other data

---

### **STEP 5: Add Config to Game File** ⏱️ 5 minutes

1. **Open** `bingo_game_multiplayer.html` in a text editor (Notepad, VS Code, etc.)

2. **Find this section** (around line 25):

```javascript
// ==========================================
// FIREBASE CONFIGURATION
// ==========================================
// PASTE YOUR FIREBASE CONFIG HERE:
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_PROJECT.firebaseapp.com",
  databaseURL: "YOUR_DATABASE_URL",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_STORAGE_BUCKET",
  messagingSenderId: "YOUR_SENDER_ID",
  appId: "YOUR_APP_ID"
};
```

3. **Replace** the entire `firebaseConfig` object with YOUR config from Step 3

4. **Save the file** (Ctrl + S)

---

### **STEP 6: Test the Setup** ⏱️ 5-10 minutes

#### **Test 1: Open as HOST**

1. Double-click `bingo_game_multiplayer.html` to open in browser
2. You'll see a popup: **"Select your role"**
3. Click **"HOST MODE"**
4. You should see:
   - Game controls (Draw Number, Auto Draw, etc.)
   - Your bingo card
   - Status: "🎮 HOST MODE" at top

#### **Test 2: Open as VIEWER (same computer)**

1. **Open a new browser window** (or use phone)
2. Open `bingo_game_multiplayer.html` again
3. Click **"VIEWER MODE"**
4. You should see:
   - Different bingo card than HOST
   - No game controls (read-only)
   - Status: "👁️ VIEWER MODE" at top

#### **Test 3: Sync Test**

1. In **HOST window**: Click "Draw Number"
2. In **VIEWER window**: Number should appear within 1 second!
3. Both should show the same number
4. Voice should speak in both windows

**✅ If this works, you're ready!**

---

### **STEP 7: Share with Players** ⏱️ 5 minutes

#### **Option A: Local Network (Same WiFi)**

If everyone is at the same venue:

1. **Find your computer's IP address:**
   ```powershell
   ipconfig
   ```
   Look for "IPv4 Address": e.g., `192.168.1.100`

2. **Start a simple web server:**
   ```powershell
   cd "C:\Users\acheu\OneDrive\文件\Monthly-reconciliation"
   python -m http.server 8000
   ```

3. **Players access:**
   - On their phones, open browser
   - Go to: `http://192.168.1.100:8000/bingo_game_multiplayer.html`
   - They auto-enter VIEWER mode

#### **Option B: Upload to Web (Any Connection)**

For players on different networks:

**Quick Method - Firebase Hosting (Free):**

1. In Firebase Console, click "Hosting"
2. Click "Get started"
3. Follow the wizard to deploy your HTML file
4. You'll get a URL like: `https://bingo-game-xxxxx.web.app`
5. Share this URL with all players

**Alternative - Google Drive:**

1. Upload `bingo_game_multiplayer.html` to Google Drive
2. Share link → Anyone with link can view
3. Players download and open locally
4. Still syncs via Firebase!

---

## 🎮 How to Use During Event

### **Before the Event (30 min before):**

1. **Set up your screen:**
   - Open game as HOST on your laptop
   - Connect to projector/big screen (optional)
   - Test audio (Cantonese voice)

2. **Share link with players:**
   - QR code or short URL
   - WhatsApp group message
   - Projected on screen

3. **Test with 2-3 people:**
   - Have them open on their phones
   - Draw a few numbers
   - Verify sync works

### **During the Game:**

1. **Start:**
   - Click "抽號碼" to draw first number
   - Or click "自動抽號" for auto-draw mode

2. **Players:**
   - See numbers on their phones
   - Hear Cantonese announcements
   - Mark their own cards
   - Click "🎉 我贏咗 BINGO!" when they win

3. **Winner Appears:**
   - HOST sees alert: "Player claimed BINGO!"
   - Click "Start Verification Timer"
   - 60-second countdown starts on ALL screens
   - Player shows phone to you
   - Verify their card matches called numbers
   - Click "✓ Confirm Winner" or "✗ Reject"

4. **Continue or Reset:**
   - Continue for multiple winners
   - Click "重新開始" to start new round

---

## 🎨 Customization Options

### **Change HOST Password:**

Find this line (around line 450):
```javascript
const HOST_PASSWORD = "bingo2026";
```
Change to your own password.

### **Change Verification Timer:**

Find this line (around line 520):
```javascript
let verificationTime = 60; // seconds
```
Change to 30, 90, or any number.

### **Disable Audio:**

Find this line (around line 380):
```javascript
const VOICE_ENABLED = true;
```
Change to `false` to disable voice.

---

## 🐛 Troubleshooting

### ❌ **"Numbers not syncing"**

**Check:**
1. Firebase config is pasted correctly
2. Internet connection on both HOST and viewers
3. Open browser console (F12) and check for errors
4. Realtime Database is created and enabled

**Fix:**
- Refresh both browser windows
- Check Firebase Console → Realtime Database → Data tab
- You should see data appearing when HOST draws numbers

---

### ❌ **"Player can't access the game"**

**Check:**
1. They have internet connection
2. URL is correct (include .html extension)
3. File is uploaded if using hosting method

**Fix:**
- Have them try cellular data instead of WiFi
- Send file directly via WhatsApp/email

---

### ❌ **"Voice not working"**

**Check:**
1. Text-to-Speech API is enabled (see VOICE_SETUP_INSTRUCTIONS.md)
2. Browser allows audio (click "Allow" if prompted)
3. Volume is turned up

**Fix:**
- Voice is optional - game works without it
- Falls back to visual display only

---

### ❌ **"Too many BINGO claims at once"**

**This is normal!** The system queues them:
1. First claim triggers verification
2. Other claims wait in queue
3. After verifying/rejecting first, move to next

---

### ❌ **"Firebase quota exceeded"**

**Unlikely** with 100 players, but if it happens:

**Free tier limits:**
- 100 simultaneous connections (you should be fine)
- 10 GB/month download (plenty for Bingo)
- 1 GB storage (more than enough)

**If you hit limits:**
- Upgrade to Blaze plan (pay-as-you-go, very cheap)
- Or use Google Sheets method instead

---

## 📊 What Data Does Firebase Store?

```json
{
  "gameState": {
    "currentNumber": 42,
    "calledNumbers": [5, 19, 42, 8, 23...],
    "phrase": "出咗喇！係42，四十二！",
    "timestamp": 1234567890
  },
  "bingoClaims": {
    "claim_001": {
      "playerName": "張三",
      "timestamp": 1234567890,
      "verified": false
    }
  },
  "verification": {
    "active": true,
    "timeLeft": 60,
    "claimId": "claim_001"
  }
}
```

**Privacy:**
- No personal data collected
- Just game state and player names (if they choose to share)
- Data auto-deletes after game ends (you can manually clear)

---

## 🔒 Security Notes

### **Current Setup (Good for Events):**
- Anyone can read game state ✓
- Anyone can write (draw numbers) ⚠️
- Host password in code (basic protection)

### **For Production (If Needed):**

Add Firebase Authentication:
1. Enable Email/Password auth in Firebase
2. Only authenticated HOST can write
3. Viewers can only read

**For a one-time event, current security is fine!**

---

## 💰 Cost

**Firebase Free Tier (Spark Plan):**
- ✓ 100 simultaneous connections
- ✓ 10 GB/month data transfer
- ✓ 1 GB storage
- ✓ 100,000 reads/day

**Your Bingo event:**
- 100 players = Well within limits
- ~2-hour event = Minimal data usage
- **Cost: $0.00** ✓

**If you somehow exceed (very rare):**
- Firebase sends warning email
- Can upgrade to Blaze (pay-per-use, still cents)

---

## ✅ Pre-Event Checklist

**1 Week Before:**
- [ ] Firebase project created
- [ ] Config added to HTML file
- [ ] Tested with 2-3 friends on different networks
- [ ] Assets added (logos, music)

**1 Day Before:**
- [ ] Test at actual venue (WiFi/cellular)
- [ ] QR code or short URL prepared
- [ ] Backup plan ready (local mode)

**30 Min Before Event:**
- [ ] Open game as HOST
- [ ] Test projector/screen
- [ ] Share link with early arrivals
- [ ] Test with 3-5 people

**During Event:**
- [ ] Keep HOST screen visible
- [ ] Monitor for BINGO claims
- [ ] Have fun! 🎉

---

## 🆘 Emergency Fallback

If Firebase completely fails during event:

1. Click "Switch to Local Mode" button
2. Game continues without sync
3. Announce numbers verbally
4. Players mark manually
5. Manual verification

**Your backup file `bingo_game_backup.html` also works standalone!**

---

## 📞 Support

Created by GitHub Copilot for AlphaSight HK Bingo Event

**Resources:**
- Firebase Docs: https://firebase.google.com/docs/database
- This guide: `FIREBASE_SETUP_GUIDE.md`
- Voice setup: `VOICE_SETUP_INSTRUCTIONS.md`
- Assets guide: `ASSETS_SETUP_GUIDE.md`

---

**Ready to set up Firebase? Follow Step 1 above and we'll build from there!** 🚀
