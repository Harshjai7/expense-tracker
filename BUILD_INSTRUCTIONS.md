# Expense Tracker → APK Build Guide

## Prerequisites (One-time Setup)

### 1. Install Node.js
- Download from: https://nodejs.org (choose LTS version)
- Verify: open terminal and run `node -v`

### 2. Install Android Studio
- Download from: https://developer.android.com/studio
- During install, make sure these are checked:
  - ✅ Android SDK
  - ✅ Android SDK Platform
  - ✅ Android Virtual Device (optional, for testing)

### 3. Set ANDROID_HOME environment variable
**Windows:**
1. Search "Environment Variables" in Start Menu
2. Under System Variables → New:
   - Variable name: `ANDROID_HOME`
   - Variable value: `C:\Users\YOUR_USERNAME\AppData\Local\Android\Sdk`
3. Edit `Path` variable → Add: `%ANDROID_HOME%\tools` and `%ANDROID_HOME%\platform-tools`

**Mac/Linux:**
Add to `~/.bashrc` or `~/.zshrc`:
```
export ANDROID_HOME=$HOME/Library/Android/sdk
export PATH=$PATH:$ANDROID_HOME/tools:$ANDROID_HOME/platform-tools
```
Then run: `source ~/.bashrc`

---

## Build Steps

### Step 1 — Open terminal in this project folder
```
cd path/to/expense-tracker-apk
```

### Step 2 — Install dependencies
```
npm install
```

### Step 3 — Add Android platform
```
npx cap add android
```

### Step 4 — Sync your web files to Android
```
npx cap sync android
```

### Step 5 — Open in Android Studio
```
npx cap open android
```
This opens Android Studio automatically.

### Step 6 — Build APK in Android Studio
1. Wait for Gradle sync to finish (bottom status bar)
2. Menu → **Build** → **Build Bundle(s) / APK(s)** → **Build APK(s)**
3. Wait for build to complete
4. Click **"locate"** in the popup to find your APK

📁 APK location: `android/app/build/outputs/apk/debug/app-debug.apk`

---

## Install APK on Your Phone

### Option A — USB Cable
1. Enable Developer Options on phone: Settings → About Phone → tap "Build Number" 7 times
2. Enable USB Debugging: Settings → Developer Options → USB Debugging ✅
3. Connect phone via USB
4. In Android Studio: Run → Run 'app' (select your phone)

### Option B — Direct Transfer
1. Copy `app-debug.apk` to your phone (via USB, Google Drive, WhatsApp, etc.)
2. On phone: tap the APK file
3. Allow "Install from unknown sources" if prompted
4. Install!

---

## App Details
- **App Name:** Expense Tracker
- **App ID:** com.expensetracker.app
- **Version:** 1.0.0
- **Min Android:** 5.1 (API 22)

---

## Troubleshooting

| Problem | Solution |
|---|---|
| `ANDROID_HOME not set` | Set environment variable (see above) |
| `Gradle sync failed` | File → Sync Project with Gradle Files |
| `SDK not found` | Android Studio → SDK Manager → install Android 13 (API 33) |
| `npm not found` | Re-install Node.js and restart terminal |
| App installs but blank screen | Check `www/index.html` exists in project folder |
