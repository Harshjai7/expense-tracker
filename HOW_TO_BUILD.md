# How to Get Your APK Using GitHub (No Android Studio Needed)

## What will happen:
You upload this project to GitHub → GitHub's servers build the APK → You download it.
Your PC does zero work!

---

## Step 1 — Create a GitHub Account
- Go to https://github.com and sign up (free)

---

## Step 2 — Create a New Repository
1. Click the **"+"** icon (top right) → **New repository**
2. Name it: `expense-tracker`
3. Set to **Public**
4. Click **Create repository**

---

## Step 3 — Upload the Project Files
On the repository page:
1. Click **"uploading an existing file"** link
2. Drag and drop ALL files from this ZIP (extract first):
   - `www/` folder
   - `package.json`
   - `capacitor.config.json`
   - `.github/` folder  ← IMPORTANT: make sure this is included!
   - `.gitignore`
3. Scroll down → click **Commit changes**

> ⚠️ If you can't see `.github` folder after extracting (it's hidden), on Windows:
> Open File Explorer → View → Check "Hidden items"

---

## Step 4 — Watch the Build
1. Go to your repository on GitHub
2. Click the **"Actions"** tab at the top
3. You'll see **"Build Android APK"** workflow running (yellow circle = in progress)
4. Wait 5–10 minutes for it to finish (green ✅ = success)

---

## Step 5 — Download Your APK
1. Click on the completed workflow run
2. Scroll down to **"Artifacts"** section
3. Click **"expense-tracker-apk"** to download
4. Extract the ZIP → you get `app-debug.apk`

---

## Step 6 — Install on Your Phone
1. Transfer `app-debug.apk` to your phone (WhatsApp, Google Drive, USB, etc.)
2. On your phone, tap the APK file
3. If prompted: **Settings → Allow install from unknown sources → Enable**
4. Tap Install → Done! 🎉

---

## Troubleshooting

| Problem | Solution |
|---|---|
| Actions tab shows no workflow | Make sure `.github/workflows/build-apk.yml` was uploaded |
| Build failed (red ❌) | Click on it → read the error → usually a missing file |
| Can't see `.github` folder | Enable hidden files in File Explorer |
| Phone says "Install blocked" | Allow unknown sources in phone settings |

---

## Re-building after changes
If you update your `index.html`:
1. Go to your GitHub repo
2. Navigate to `www/index.html` → click pencil icon → edit → commit
3. GitHub will automatically rebuild the APK!
