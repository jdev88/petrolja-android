# PetrolJA Android App

## How this works
This project uses Capacitor to wrap the PetrolJA web app into a native Android APK.
The APK is built automatically in the cloud using GitHub Actions — no Android Studio needed.

## To build a new APK (all in browser, no local tools needed)

1. Push any change to the `main` branch on GitHub
2. Go to your repo → Actions tab → "Build Android APK" workflow
3. Click "Run workflow" if you want to trigger manually
4. Wait ~5 minutes for the build to finish
5. Click the completed run → scroll to "Artifacts" → download `petrolja-debug-apk`
6. Install the APK on any Android phone for testing

## Folder structure
```
petrolja-android/
  capacitor.config.json   ← app settings (name, ID, colours)
  package.json            ← dependencies
  www/                    ← your web app files go here
    index.html
    PetrolJA-mobile.html
    manifest.json
    icon-192.png
    icon-512.png
  .github/
    workflows/
      build-apk.yml       ← the cloud build script
```

## To update the app
1. Replace files in the `www/` folder with updated versions
2. Commit and push to GitHub
3. GitHub Actions automatically builds a new APK

## For Play Store submission
The workflow builds an unsigned release APK.
To sign it for the Play Store you need to:
1. Create a keystore file (one time)
2. Add it as a GitHub Secret
3. Update the workflow to sign the APK

Ask Claude to help you with the signing step when you're ready.
