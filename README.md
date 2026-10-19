# 313 — Knowledge

This repository reuses the existing 313 web app and adds a deployment workflow for:
- a free website hosted on GitHub Pages;
- an Android APK built automatically by GitHub Actions.

## 1) Publish the website and build the APK

1. Create a **public** repository on GitHub named `313-app`.
2. On your computer, extract this ZIP file.
3. Upload the **contents** of this folder to the repository root (not the folder itself).
   Make sure `index.html`, `web/`, `package.json`, `capacitor.config.json`, and `.github/` are visible at the root.
4. Commit the files to the `main` branch.
5. In GitHub, open **Settings → Pages**. Under **Build and deployment → Source**, select **GitHub Actions**.
6. Open the **Actions** tab. Wait for the workflow named **Publish 313 website and build Android APK** to finish successfully.
7. In the website job, copy the published Pages URL. It will usually look like `https://YOUR-USERNAME.github.io/313-app/`.
8. In the Android job/run, open the workflow run, scroll to **Artifacts**, and download `313-knowledge-android-apk`. Extract the ZIP to get `app-debug.apk`.

## 2) Install the APK on your Android phone

1. Transfer `app-debug.apk` to your phone.
2. Open the file and follow Android's prompt to allow installation from that source if prompted.
3. Install and launch **313 Knowledge**.

Only install APKs you built yourself or trust. The workflow creates a **debug APK** for testing, not a Play Store-signed release. Publishing on Google Play requires a signed release build and a Play Console developer account.

## 3) Work on the app later

- Edit `web/index.html` to change the website/app UI.
- Also copy updated web assets to the root `index.html` if you want the root copy to remain current. GitHub Pages publishes from `web/`.
- Push commits to `main`. The website redeploys and a new APK artifact is generated automatically.

## Notes

- Hosting and GitHub Actions are free within GitHub's applicable usage limits.
- This project packages the current HTML app; it does not add user accounts, cloud sync, payments, or a content-management backend.
- Review sample article claims and add trustworthy source links before launching publicly.
