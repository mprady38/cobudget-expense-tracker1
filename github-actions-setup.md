# Enable GitHub Actions for APK Building

The automatic build isn't starting because GitHub Actions needs to be enabled. Here's how to fix it:

## Step 1: Enable GitHub Actions

1. **Go to your repository** on GitHub
2. **Click "Settings" tab** (next to Code, Issues, Pull requests)
3. **Scroll down to "Actions"** in the left sidebar
4. **Click "General"** under Actions
5. **Select "Allow all actions and reusable workflows"**
6. **Click "Save"**

## Step 2: Manually Trigger First Build

Since the build didn't start automatically:

1. **Click "Actions" tab** in your repository
2. **Click "Build Android APK"** on the left side
3. **Click "Run workflow"** button (top right)
4. **Select "main" branch**
5. **Click green "Run workflow" button**

## Step 3: Alternative - Make a Small Change

If the manual trigger doesn't work:

1. **Edit any file** in your repository (like README.md)
2. **Add a space or line** at the end
3. **Commit the change**
4. This will trigger the workflow automatically

## What You Should See After Enabling

- **Actions tab** becomes active
- **Workflows** section shows "Build Android APK"
- **Green "Run workflow" button** appears
- **Build status** shows in progress (yellow circle)

## Expected Build Process

Once triggered:
- **Setup environments** (Node.js, Java, Android SDK)
- **Install dependencies** (npm packages)
- **Build web app** (React compilation)
- **Create APK** (Android build)
- **Upload to Releases** (automatic download link)

## Timeline
- **Build duration**: 10-15 minutes
- **Result**: Downloadable APK file in Releases section

Try enabling Actions in Settings first, then manually trigger the workflow.