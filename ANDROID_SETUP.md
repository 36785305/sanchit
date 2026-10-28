# Android setup notes

The Android folder contains the manifest permissions and MainActivity entry point. Flutter's generated Gradle files and resources are intentionally not bundled; create them with `flutter create .` from this folder using a current Flutter SDK, then run `flutter pub get`.

If Flutter reports a package API/version conflict, use `flutter pub outdated` and adjust dependency versions for your installed Flutter SDK.
