# Firebase Setup Guide

## 📋 Quick Setup (10 minutes)

Your framework now uses Firebase for real-time collaboration! Users just enter their name - no tokens needed.

---

## 🚀 Step 1: Create Firebase Project

1. Go to: https://console.firebase.google.com/
2. Click **"Add project"**
3. Project name: **"design-skills-framework"** (or any name)
4. Click **Continue**
5. Disable Google Analytics (not needed)
6. Click **Create project**
7. Wait ~30 seconds, then click **Continue**

---

## 🔧 Step 2: Set Up Realtime Database

1. In Firebase Console, click **Realtime Database** (left sidebar)
2. Click **Create Database**
3. Location: Choose **europe-west1** (closest to LEGO offices)
4. Security rules: Start in **test mode**
5. Click **Enable**

---

## 🔐 Step 3: Configure Security Rules

1. Click on the **Rules** tab
2. Replace the rules with:

```json
{
  "rules": {
    "framework": {
      ".read": true,
      ".write": true
    },
    "activeUsers": {
      ".read": true,
      ".write": true
    },
    "lastUpdated": {
      ".read": true,
      ".write": true
    }
  }
}
```

3. Click **Publish**

**Note:** These rules allow anyone to read/write. For production, you can add authentication.

---

## 🔑 Step 4: Get Your Firebase Config

1. Click the **⚙️ Settings icon** → **Project settings**
2. Scroll down to **"Your apps"**
3. Click the **</>** (Web) icon
4. App nickname: **"Design Skills Web App"**
5. Click **Register app**
6. Copy the `firebaseConfig` object (looks like this):

```javascript
const firebaseConfig = {
  apiKey: "AIzaSy...",
  authDomain: "design-skills-framework.firebaseapp.com",
  databaseURL: "https://design-skills-framework-default-rtdb.europe-west1.firebasedatabase.app",
  projectId: "design-skills-framework",
  storageBucket: "design-skills-framework.appspot.com",
  messagingSenderId: "123456789012",
  appId: "1:123456789012:web:abc123def456"
};
```

---

## 📝 Step 5: Update index.html

1. Open `index.html` in your editor
2. Find the line (around line 436):
   ```javascript
   const firebaseConfig = {
   ```
3. Replace the dummy config with your actual config from Step 4
4. Save the file

---

## 🚀 Step 6: Commit and Push

```bash
cd "/Users/dkMicHei/Downloads/designer-future-roles-framework"
git add index.html
git commit -m "Configure Firebase with real credentials"
git push origin main
```

---

## ✅ Step 7: Test It!

1. Open: https://michaelheiderlego.github.io/designer-future-roles-framework/
2. You should see: "Welcome! 👋 Please enter your name"
3. Enter your name
4. Add an item
5. Open in another browser/device
6. You should see the item appear in real-time!

---

## 🎯 How It Works for Users

### First Visit:
1. User opens the site
2. Popup: "Welcome! 👋 Please enter your name: ______"
3. User types their name
4. That's it - they can start editing!

### What They See:
- **Top banner**: "Editing as [their name]"
- **Also editing**: Shows other active users
- **Auto-sync**: Changes save instantly, appear for everyone in real-time

### No More:
- ❌ GitHub tokens
- ❌ Account creation
- ❌ Complex authentication
- ❌ Manual refresh to see changes

---

## 🔒 Security Options

### Current Setup (Test Mode):
- Anyone can read/write
- Good for internal LEGO team
- Quick to set up

### For Production (Optional):
You can add email authentication later:

```json
{
  "rules": {
    "framework": {
      ".read": "auth != null",
      ".write": "auth != null"
    }
  }
}
```

Then users sign in with email/password (still simpler than GitHub tokens).

---

## 💰 Pricing

**Free tier includes:**
- 1 GB stored data
- 10 GB/month downloaded
- 100 simultaneous connections

Your framework is tiny (~50 KB), so free tier is plenty!

---

## 🆘 Troubleshooting

### "Firebase not configured"
- Check that you updated `firebaseConfig` in index.html
- Make sure all fields are filled in correctly
- Verify the `databaseURL` is correct

### "Error saving - check connection"
- Check Security Rules are published
- Verify database is in test mode or has proper rules
- Check browser console for detailed errors

### Users can't see each other's changes
- Hard refresh: Cmd/Ctrl + Shift + R
- Check that everyone is on the same URL
- Verify Firebase is initialized (check browser console)

---

## 📊 Monitoring Usage

1. Go to Firebase Console
2. Click **Realtime Database**
3. See live data and active connections
4. Check **Usage** tab for stats

---

## 🎉 Done!

Your team can now collaborate in real-time with just their names!

**Share this link:**
👉 https://michaelheiderlego.github.io/designer-future-roles-framework/

**User instructions:**
1. Open the link
2. Enter your name when prompted
3. Start adding skills, checkpoints, and tools!

---

## Questions?

Check the Firebase documentation: https://firebase.google.com/docs/database
