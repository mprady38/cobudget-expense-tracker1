# CoBudget APK - GitHub Actions Build

Since VoltBuilder isn't working, I've set up automated APK building through GitHub Actions. This will generate your APK file automatically and make it downloadable.

## How It Works

GitHub Actions will:
- Build your APK automatically when you push code
- Create downloadable APK files in GitHub releases
- Handle all the Android build environment setup
- Generate debug APK perfect for installing on your phones

## Setup Process

### Step 1: Push to GitHub
Your project needs to be in a GitHub repository. If it's not already:
1. Create new repository on GitHub
2. Push your CoBudget project code
3. The GitHub Actions workflow is already configured

### Step 2: Automatic Build
Once pushed, GitHub will:
- Detect the workflow file
- Start building your Android APK
- Take about 10-15 minutes to complete

### Step 3: Download APK
After build completes:
1. Go to your GitHub repository
2. Click "Releases" section
3. Download the APK file from the latest release

## Alternative: Manual Trigger
You can also trigger builds manually:
1. Go to your GitHub repository
2. Click "Actions" tab
3. Select "Build Android APK" workflow
4. Click "Run workflow"

## Expected Output
- **File**: `app-debug.apk`
- **Size**: ~15-20MB
- **Ready for**: Direct installation on Android phones

## Installation on Phones
1. Download APK from GitHub releases
2. Enable "Install unknown apps" in Android settings
3. Transfer to both phones and tap to install

## Benefits
- **Free**: No cost with GitHub account
- **Automated**: Builds happen automatically
- **Reliable**: Uses standard Android build tools
- **Repeatable**: New APK for every update

This approach bypasses VoltBuilder entirely and gives you a reliable way to generate APK files whenever you need them.