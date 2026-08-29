# flare-android-project

## Purpose
Android Studio / Gradle + NDK project that compiles engine `src/` into application `org.flare.app`.

## Ownership
- Gradle wrapper and project files: `settings.gradle`, `build.gradle`, `gradle.properties`, `app/build.gradle`.
- App: `app/src/main/AndroidManifest.xml`, `app/src/main/java/org/flare/app/FLARE.java`, resources under `app/src/main/res/`.
- NDK: `app/src/main/jni/Android.mk`, `Application.mk`, `src/Android.mk`, `src/Android_static.mk` (lists `../../../../../../src/*.cpp`).
- `README.android` — Android build steps.
- Git submodules (`.gitmodules`): `app/src/main/jni/SDL2`, `SDL2_image`, `SDL2_mixer`, `SDL2_ttf` (upstream libsdl-org). Do not document those trees as FLARE source.
- `app/src/main/java/org/libsdl/app/` — vendored SDL Java activity/HID helpers.

## Local Contracts
- `applicationId` / namespace: `org.flare.app`. `compileSdkVersion` 30, `minSdkVersion` 16, `targetSdkVersion` 29 (`app/build.gradle`).
- `Application.mk`: `APP_ABI` armeabi-v7a arm64-v8a x86 x86_64; `APP_PLATFORM` android-16; `APP_STL` c++_static.
- Java compile depends on a custom `ndkBuild` task (`ndk-build` in `app/src/main`).
- `README.android`: place SDL2 libraries under `jni/`; disable JPG/WEBP in SDL2_image and MOD/SMPEG in SDL2_mixer Android.mk as documented there.
- Adding engine sources requires updating `app/src/main/jni/src/Android.mk` `LOCAL_SRC_FILES` as well as root `CMakeLists.txt`.

## Work Guidance
- Follow `README.android` for JDK, Android Studio, NDK, and SDL library layout. This project is not built by `.github/workflows/main.yml`.

## Verification

## Child DOX Index
- No nested AGENTS.md. Skip SDL submodule checkouts and Gradle/IDE generated dirs listed in `.gitignore`.
