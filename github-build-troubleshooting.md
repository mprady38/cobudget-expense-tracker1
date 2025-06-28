# GitHub Actions Build Error - Troubleshooting

Your build encountered an error. Here's how to diagnose and fix it:

## Step 1: View the Error Details
1. **Click on the failed workflow** (red X or yellow circle)
2. **Click on the job name** (usually "build")
3. **Expand the failed step** to see the error message
4. **Copy the error text** to share with me

## Common Build Errors and Solutions

### Error: "npm ci" fails
**Cause**: Missing package-lock.json or dependency issues
**Solution**: Check if package-lock.json was uploaded

### Error: "npm run build" fails
**Cause**: Build script missing or TypeScript errors
**Solution**: Add ionic:build script to package.json

### Error: "npx cap sync" fails
**Cause**: Missing Android platform or Capacitor config
**Solution**: Check if android/ folder uploaded properly

### Error: "./gradlew assembleDebug" fails
**Cause**: Android SDK setup or Gradle permissions
**Solution**: Usually fixes itself on retry

### Error: "Permission denied" on gradlew
**Cause**: File permissions issue
**Solution**: Already handled in workflow with chmod +x

## Quick Fixes

### Missing package.json script
If build fails on "npm run build", we need to add:
```json
"scripts": {
  "ionic:build": "vite build"
}
```

### Missing files
Common missing files that cause failures:
- `package-lock.json`
- `android/` folder
- `capacitor.config.ts`
- `dist/` folder (gets built during workflow)

## Next Steps
1. **Share the specific error message** you see
2. **I'll provide the exact fix** for your error
3. **Update the repository** with the fix
4. **Re-run the workflow** (automatic or manual)

The build system is robust - most errors are quick fixes!