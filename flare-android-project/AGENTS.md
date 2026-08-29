# flare-android-project

## Purpose
Android Gradle/NDK project that builds the engine as `org.flare.app`.

## Ownership
Owns the Gradle project, `app/` Java/NDK glue, and `README.android`. Engine C++ stays in `/src`. SDL2, SDL2_image, SDL2_mixer, and SDL2_ttf under `app/src/main/jni/` are git submodules (see root `.gitmodules`); do not treat them as Flare sources.

## Local Contracts
- Application id `org.flare.app`; `minSdkVersion` 16; `targetSdkVersion` 29; `compileSdkVersion` 30 (`app/build.gradle`).
- Native build is `ndk-build` on `app/src/main`, not Gradle’s generated Android.mk. `app/src/main/jni/src/Android.mk` lists engine sources as `../../../../../../src/*.cpp`.
- `Application.mk`: `APP_ABI` armeabi-v7a arm64-v8a x86 x86_64; `APP_PLATFORM` android-16; `APP_STL` c++_static.
- `README.android`: in `SDL2_image/Android.mk` set `SUPPORT_JPG` and `SUPPORT_WEBP` to false; in `SDL2_mixer/Android.mk` set `SUPPORT_MOD_MIKMOD` and `SUPPORT_MP3_SMPEG` to false.
- Vendored `SDL2_image` under `jni/` may predate 2.6.0 or omit SVG. Engine SVG loading is compile-time gated on `IMG_LoadSizedSVG_RW`; PNG still loads.
- F-Droid/Play store listing copy and screenshots live in root `fastlane/metadata/android/`.

## Work Guidance
`README.android`: JDK, Android Studio, NDK, SDK platform; place SDL libraries under `jni/` (submodules fill this when initialized). Adding engine sources requires updating both root `CMakeLists.txt` and `app/src/main/jni/src/Android.mk`.

## Verification

## Child DOX Index
No child AGENTS.md. Skip `app/src/main/jni/SDL2*` (upstream SDL) and `app/src/main/java/org/libsdl/` (upstream SDL Java).
