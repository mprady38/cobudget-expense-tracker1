# Upload Missing GitHub Workflow Files

Some files didn't extract properly. Here are the missing files you need to add to your GitHub repository:

## Missing File 1: .github/workflows/build-android.yml

Create this folder structure in your repository:
- Create folder: `.github`
- Inside `.github`, create folder: `workflows`
- Inside `workflows`, create file: `build-android.yml`

Copy this content into `build-android.yml`:

```yaml
name: Build Android APK

on:
  push:
    branches: [ main, master ]
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout code
      uses: actions/checkout@v4

    - name: Setup Node.js
      uses: actions/setup-node@v4
      with:
        node-version: '20'
        cache: 'npm'

    - name: Setup Java
      uses: actions/setup-java@v4
      with:
        distribution: 'temurin'
        java-version: '17'

    - name: Install dependencies
      run: npm ci

    - name: Build web app
      run: npm run build

    - name: Sync Capacitor
      run: npx cap sync android

    - name: Set permissions for gradlew
      run: chmod +x android/gradlew

    - name: Build debug APK
      run: |
        cd android
        ./gradlew assembleDebug

    - name: Upload APK artifact
      uses: actions/upload-artifact@v4
      with:
        name: CoBudget-APK
        path: android/app/build/outputs/apk/debug/app-debug.apk

    - name: Create release
      if: github.ref == 'refs/heads/main' || github.ref == 'refs/heads/master'
      uses: softprops/action-gh-release@v1
      with:
        tag_name: v${{ github.run_number }}
        name: CoBudget v${{ github.run_number }}
        files: android/app/build/outputs/apk/debug/app-debug.apk
        body: |
          CoBudget Android APK - Debug Build
          
          Install instructions:
          1. Enable "Install unknown apps" in Android Settings
          2. Download and tap the APK file to install
          3. Login with your Google account to start tracking expenses
      env:
        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

## How to Add This File

1. **Go to your GitHub repository**
2. **Click "Create new file"**
3. **Type**: `.github/workflows/build-android.yml`
4. **Paste the content above**
5. **Commit the file**

## After Adding the File

The APK build will start automatically once you commit this workflow file.

## Alternative: Direct Upload Method

If creating folders is difficult:
1. **Download the corrected files** from this project
2. **Create a new ZIP** with proper folder structure
3. **Re-upload to GitHub**

Once this workflow file is added, your automatic APK builds will work.