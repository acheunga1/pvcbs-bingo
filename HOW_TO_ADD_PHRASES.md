# 🎭 How to Add More Fun Phrases to Your Bingo Game

## What's New? 🎉

Your Bingo game now has a **fun Cantonese host personality** that says entertaining phrases instead of just numbers!

### Features:
1. **5 Types of Phrases:**
   - **Standard** - Normal announcements with personality
   - **Exciting** - High energy, encouraging
   - **Playful** - Interactive, fun
   - **Special** - For special moments
   - **Teasers** - Spoken before revealing the number (40% chance)

2. **Lucky Number Comments:**
   - Special remarks for lucky numbers (8, 18, 88, 66, 69, etc.)
   - Automatically added after the main phrase

3. **Varied Timing:**
   - Auto-draw now waits 2-4 seconds randomly (more exciting!)
   - Sometimes speaks a teaser before showing the number

4. **Bigger Text Display:**
   - Room for longer, entertaining phrases

---

## Example Phrases You'll Hear:

### When drawing number 19:
- "下一個號碼係19！十九！"
- "出咗喇！係19，十九！"
- "十九！19呀！有冇人中？"
- "你哋嗌大聲啲！我聽到喇！係19，十九！"

### With lucky numbers (18):
- "好運嚟喇！18呀！十八！要發！"
- "出咗喇！係18，十八！要發！"

### Before revealing (teaser):
- "嚟緊嗰個號碼會係邊個呢？" → (2 second pause) → "嚟喇嚟喇！25，二十五！"

---

## How to Add Your Own Phrases

### Step 1: Open the Game File
Open `bingo_game.html` in a text editor

### Step 2: Find the Phrase Section
Search for: `const bingoCallPhrases = {`
(Around line 420)

### Step 3: Add to Any Category

**Format:** Use `{num}` for the number and `{cantonese}` for Chinese text

#### Example - Add to "exciting" category:
```javascript
exciting: [
    '{num}！{cantonese}！啱唔啱你用先？',
    '{cantonese}！{num}呀！有冇人中？',
    // ADD YOUR NEW PHRASE HERE:
    '好sharp呀！{num}號！{cantonese}！快啲mark低！',
    '睇下係咪你要嘅？{num}，{cantonese}！好彩喇！'
],
```

#### Example - Add teaser phrases:
```javascript
teasers: [
    '嚟緊嗰個號碼會係邊個呢？',
    '你哋準備好未呀？下一個嚟喇！',
    // ADD YOUR NEW TEASER:
    '呢個可能令你賓果喇！',
    '邊個最好運呢？睇下啦！'
],
```

### Step 4: Add Lucky Number Comments

Search for: `const luckyNumberComments = {`

```javascript
const luckyNumberComments = {
    8: '發發發！好意頭呀！',
    18: '要發！',
    // ADD YOUR OWN:
    21: '廿一點！',
    77: '雙拐杖！',
    // Any number you want!
};
```

### Step 5: Save and Refresh
Save the file and refresh your browser. Try drawing numbers to hear your new phrases!

---

## Tips for Writing Great Phrases

### ✅ Good Phrases:
- **Short and punchy** - Easy to understand
- **Use Cantonese slang** - "好sharp呀！", "勁呀！", "發咗！"
- **Ask questions** - "啱唔啱你用先？", "有冇人中？"
- **Build excitement** - "好彩嚟喇！", "差少少就賓果！"
- **Interactive** - Reference the players ("你哋", "大家")

### ❌ Avoid:
- Very long phrases (takes too long to speak)
- English words (unless intentional Cantonese-English mix)
- Formal/written Chinese (keep it casual spoken Cantonese)

---

## Adjust Phrase Frequency

Find this section (around line 480):
```javascript
// 30% chance for exciting, 30% playful, 20% special, 20% standard
const rand = Math.random();
if (rand < 0.3) {
    phraseType = 'exciting';
} else if (rand < 0.6) {
    phraseType = 'playful';
} else if (rand < 0.8) {
    phraseType = 'special';
} else {
    phraseType = 'standard';
}
```

**Change the numbers** to adjust frequency:
- `< 0.3` = 30% chance
- `< 0.6` = next 30% (total 60%)
- `< 0.8` = next 20% (total 80%)
- `else` = remaining 20% (total 100%)

**Example - More exciting phrases:**
```javascript
if (rand < 0.5) {  // 50% exciting
    phraseType = 'exciting';
} else if (rand < 0.75) {  // 25% playful
    phraseType = 'playful';
} else if (rand < 0.9) {  // 15% special
    phraseType = 'special';
} else {  // 10% standard
    phraseType = 'standard';
}
```

---

## Adjust Teaser Frequency

Find this line (around line 556):
```javascript
if (Math.random() < 0.4) {  // 40% chance
```

**Change 0.4 to:**
- `0.2` = 20% chance (less frequent)
- `0.6` = 60% chance (more frequent)
- `0` = Never show teasers
- `1` = Always show teasers

---

## Adjust Auto-Draw Timing

Find this line (around line 740):
```javascript
const delay = 2000 + Math.random() * 2000; // 2-4 seconds
```

**Change timing:**
- `const delay = 1500 + Math.random() * 1000;` = 1.5-2.5 seconds (faster)
- `const delay = 3000 + Math.random() * 3000;` = 3-6 seconds (slower)
- `const delay = 2000;` = Always exactly 2 seconds (no variation)

---

## Common Cantonese Slang for Bingo

### Numbers:
- 幾多號？ (What number?)
- 中咗！ (Got it!)
- 差一個！ (One more!)
- 賓果喇！ (Bingo!)

### Excitement:
- 好sharp呀！ (So sharp/cool!)
- 勁呀！ (Awesome!)
- 巴閉呀！ (Impressive!)
- 正呀！ (Great!)

### Luck:
- 好彩！ (Lucky!)
- 好運！ (Good luck!)
- 發達喇！ (Getting rich!)
- 意頭好！ (Good fortune!)

### Interactive:
- 有冇人中？ (Anyone got it?)
- 啱唔啱你用？ (Is this yours?)
- 聽住聽住！ (Listen up!)
- 準備好未？ (Ready?)

---

## Example: Full Custom Phrase Set

Want a really energetic host? Here's an example:

```javascript
exciting: [
    '嘩！{num}呀！{cantonese}！靚仔靚女！',
    '爆！！！{cantonese}！{num}號！邊個中咗？',
    '正呀！{num}！{cantonese}！快啲mark低佢啦！',
    '巴閉巴閉！{cantonese}出咗！{num}號！',
    '嚟喇嚟喇！{num}，{cantonese}！差唔多賓果未呀？',
],
```

---

## Need Help?

1. Make sure `{num}` and `{cantonese}` are spelled correctly
2. Don't forget the commas between phrases
3. Keep quotes matching (use `'` or `"` consistently)
4. Test after each change by refreshing the browser

**Have fun creating your custom Bingo host! 恭喜發財！🎊**
