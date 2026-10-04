# Clinic Records (works offline, data stays on the phone)

Default password: **clinic** (change it in Admin).

## Quick try (no APK)
Put these files on any HTTPS web host (GitHub Pages, Netlify, Cloudflare Pages are free).
Open the link in Chrome on your phone, menu -> "Install app" / "Add to Home screen".
It then opens like a normal app and works offline.

## Make an APK
**Option A - PWABuilder (no coding)**
1. Host the files over HTTPS as above.
2. Go to pwabuilder.com, enter your site link, choose Android and download the package.
3. Install the APK on your phone (allow "install unknown apps").

**Option B - Capacitor (needs a computer with Node + Android Studio)**

    npm init -y && npm i @capacitor/core @capacitor/cli @capacitor/android
    npx cap init "Clinic Records" com.example.clinic --web-dir=.
    npx cap add android
    npx cap sync
    npx cap open android      # then Build > Build APK in Android Studio

## Notes
- Records are stored in the app's own storage on the phone. Clearing app data or
  uninstalling erases them, so use Admin > "Download backup file" regularly.
- The password is a lock on the screen. It does not encrypt the stored data.
- Receipts are PDFs made on the phone. Admin sets the clinic name, doctor, phone and address.
