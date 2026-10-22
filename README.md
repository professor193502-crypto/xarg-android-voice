# XARG Android Voice Companion (Cloud Build)

This is an **uncompiled starter project**, not an APK. It adds:
- A movable floating XARG bubble.
- Tap-to-talk speech recognition using Android's installed recognition service.
- Spoken replies using Android Text-to-Speech.
- Typing fallback.
- A GitHub Actions workflow to attempt a debug APK build in the cloud.

**Not included:** always-listening wake word, background hotword detection, Play Store release signing, or a verified production integration. Speech recognition availability/language depends on the Android device and its installed services. This project has not been compiled or device-tested in this environment.

## Build from an Android phone
1. Create a repository on GitHub.
2. Upload the contents of this ZIP to the repository root. Include the hidden `.github/workflows/build-apk.yml` file. If using GitHub's mobile website, it may be easier to use GitHub's browser desktop mode.
3. Open the repository's **Actions** tab and enable workflows if GitHub asks.
4. Choose **Build XARG Android APK**, then **Run workflow**.
5. If the run succeeds, open it and download the `XARG-debug-APK` artifact.
6. Extract the downloaded artifact and install the APK on your Android phone. Android may ask you to allow installs from that browser/file manager.
7. Open XARG, allow microphone permission, then allow display-over-other-apps permission. Tap the floating bubble, then tap **Voice** to speak. XARG reads answers aloud.

## Important
- The app calls the existing endpoint `https://xarg-2gxfwj.v2.appdeploy.ai/api/chat`. That endpoint's current response shape and availability have not been verified by this starter project.
- No API secret is embedded in the Android source.
- Do not treat this as a production-secure public release until endpoint access, authentication/rate limits, privacy, and error handling are reviewed.
- A failed GitHub build means the starter code needs a fix; do not assume an APK was created.
