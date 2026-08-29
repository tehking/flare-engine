# flare-ios-project

## Purpose
Xcode project that builds the engine for iOS.

## Ownership
Owns `FLARE.xcodeproj`, `FLARE/` assets, `Info.plist`, and `README.md`. Engine C++ stays in `/src`. SDL libraries cloned into `libs/` (per README) are external, not Flare sources.

## Local Contracts
- Open `FLARE.xcodeproj` in Xcode to build.
- `README.md` setup: create `flare-ios-project/libs` and clone SDL, SDL_image, SDL_mixer, SDL_ttf into it (hg.libsdl.org URLs in that README).
- Vendored SDL_image in `libs/` may predate 2.6.0 or omit SVG. Engine SVG loading is compile-time gated on `IMG_LoadSizedSVG_RW`; PNG still loads.
- The Xcode project embeds the repo `mods/` folder. To run a game, copy flare-game mods into `mods/` so they are bundled.
- README notes resolution issues and that device/IPA packaging were unfinished at the time it was written.

## Work Guidance
Follow `README.md` in this directory for environment setup. Tested historically on Mac OS X 10.9.5 / Xcode 6.2 per that file.

## Verification

## Child DOX Index
No child AGENTS.md.
