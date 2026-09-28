# Milk Diary – APK project

## Option A: build in the cloud (no software to install)
1. Create a free account at github.com and make a new repository (private is fine).
2. Upload everything from this folder, including the hidden `.github` folder.
   (If `.github` won't upload: Add file > Create new file, name it `.github/workflows/build-apk.yml`, paste the contents of that file.)
3. Open the repository's **Actions** tab. The "Build APK" run starts on its own (about 5 minutes).
4. Open the finished run, download **milk-diary-apk** from Artifacts, unzip it and copy `app-debug.apk` to your phone.
5. On the phone, open the APK and allow "Install unknown apps" when asked.

## Option B: build on your computer
Needs Node 18+, JDK 17 and Android Studio (for the Android SDK).
    npm install
    npx cap add android
    npx cap sync android
    cd android && ./gradlew assembleDebug
APK: android/app/build/outputs/apk/debug/app-debug.apk

Records are stored inside the app private storage on the phone.
Uninstalling the app erases them, so use Settings > Backup first.
