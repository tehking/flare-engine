# flare-ios-project

## Purpose
Xcode iOS project (`FLARE.xcodeproj`) that builds the engine for iPhone OS.

## Ownership
- `FLARE.xcodeproj/` — Xcode project.
- `Info.plist`, `FLARE/Images.xcassets/`.
- `README.md` — environment setup (historical Mercurial clones of SDL into `flare-ios-project/libs`).

## Local Contracts
- `README.md`: copy mods into `flare-engine/mods`; the Xcode project embeds the mods folder into the bundle. Tested note in that README: Mac OS X 10.9.5, Xcode 6.2.
- Engine C++ still lives in `/src`; this folder is the iOS wrapper only.
- This project is not built by `.github/workflows/main.yml`.

## Work Guidance
- Follow `README.md` in this folder for SDL library checkout and Xcode build.

## Verification

## Child DOX Index
- No nested AGENTS.md. Skip `xcuserdata` local Xcode state.
