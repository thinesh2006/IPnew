# Tamil IPTV Auto — reconstructed starter project

This is a **starter reconstruction**, not a tested replacement APK. It carries forward the recovered HTML interface from the supplied APK and adds an Android Media3 `MediaLibraryService` intended to expose the Tamil playlist as an audio-first Android Auto media library.

## Important limitations

- This project has not been compiled or tested against a real Android Auto head unit in this environment.
- The playlist is a community-maintained list. Streams may be offline, blocked, video-only, or incompatible with ExoPlayer. The media service currently exposes playlist entries as audio items; it cannot guarantee every stream will work.
- Android Auto is not a general-purpose video player. Video remains in the phone app; parked-video support is a separate Android Automotive OS project and is not implemented here.
- The HTML interface loads HLS.js from a CDN, so it requires internet access. Existing HTML may need adjustments for WebView-specific behavior.
- This reconstruction may not preserve every original native feature. The original APK's signing key is unavailable, so a new build will not install as an in-place update unless signed with the original key.

## Build without installing Android Studio locally (GitHub Actions)

1. Create a private repository on GitHub.
2. Upload the contents of this folder (not the parent folder) to that repository.
3. Open **Actions** and enable workflows if prompted.
4. Choose **Build Tamil IPTV APK** → **Run workflow**.
5. When it finishes, open the run and download the `Tamil-IPTV-debug-apk` artifact.
6. Extract `app-debug.apk` and install it on a test phone. Android may ask you to allow installation from the browser/file manager.

This creates a debug APK for testing, not a Play Store release. Do not install it over the original app unless you are prepared to uninstall the original first; uninstalling may remove local favorites/data.

## Technical notes

- Application ID: `com.thinesh.iptvtamil`
- Version: `1.1-auto-preview`
- Target SDK: 28 for initial compatibility testing; review current Android/Google car-app distribution requirements before publishing.
- Media dependencies: AndroidX Media3 1.5.1.
