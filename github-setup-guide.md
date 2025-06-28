# Setup GitHub Repository for CoBudget APK Building

Follow these steps to get your CoBudget project on GitHub and automatically build APK files.

## Step 1: Create GitHub Account
1. Go to [github.com](https://github.com)
2. Click "Sign up" 
3. Use your email: mpradyumna38@gmail.com
4. Verify your account

## Step 2: Create New Repository
1. Click the "+" icon in top right → "New repository"
2. Repository name: `cobudget-expense-tracker`
3. Description: `Personal expense tracking app for two users with mobile APK generation`
4. Set to **Public** (required for free GitHub Actions)
5. Check "Add a README file"
6. Click "Create repository"

## Step 3: Upload Your Project
You have two options:

### Option A: Upload via Web Interface (Easier)
1. In your new repository, click "uploading an existing file"
2. Select all your project files:
   - All folders: `client/`, `server/`, `shared/`, `android/`
   - All config files: `package.json`, `capacitor.config.ts`, etc.
   - The new `.github/` folder with workflow
3. Commit message: "Initial CoBudget mobile app setup"
4. Click "Commit changes"

### Option B: Git Commands (Advanced)
```bash
git init
git add .
git commit -m "Initial CoBudget mobile app setup"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/cobudget-expense-tracker.git
git push -u origin main
```

## Step 4: Automatic APK Build
Once uploaded, GitHub will:
1. Detect the workflow file
2. Start building your Android APK automatically
3. Take 10-15 minutes to complete
4. Create a downloadable release

## Step 5: Download Your APK
1. Go to your repository page
2. Click "Actions" tab to watch build progress
3. Once complete, click "Releases" 
4. Download `app-debug.apk` file

## Step 6: Install on Phones
1. Enable "Install unknown apps" in Android Settings
2. Transfer APK to both phones (email/Drive)
3. Tap APK file to install CoBudget

## Important Files to Upload
Make sure these are included:
- `.github/workflows/build-android.yml` (the build script I created)
- `android/` folder (complete Android platform)
- `dist/` folder (your built web app)
- `capacitor.config.ts` (mobile configuration)
- `package.json` (dependencies)

## What Happens Next
- Every time you push changes, a new APK gets built
- Download updated APKs from the Releases section
- Install new versions on your phones when needed

The GitHub approach is more reliable than third-party services and gives you complete control over your mobile app builds.