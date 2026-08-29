# distribution

## Purpose
Packaging assets and scripts: desktop entry, man page, icons, Windows NSIS, Linux/Steam Runtime, macOS helpers, and Emscripten.

## Ownership
Owns files under `distribution/`. CMake install rules in root `CMakeLists.txt` consume `flare.desktop.in`, `flare.man`, and `flare_logo_icon.svg`. Game-data files named in Windows/Linux packaging scripts come from flare-game, not this tree.

## Local Contracts
- CMake configure writes `flare.desktop` from `flare.desktop.in`. Install destinations: man page `flare.man` → `man6/flare.6`; icon `flare_logo_icon.svg` → `share/icons/hicolor/scalable/apps/flare.svg`.
- `nsis_script.nsi` must not be run from this directory. It is copied to a staging dir that also includes `flare.exe`, SDL DLLs, and flare-game files (`CREDITS.txt`, `LICENSE.txt`, `README.md`, `mods/fantasycore`, `mods/empyrean_campaign`, and related mods listed in the script header).
- `emscripten/make_emscripten.sh` requires a path to flare-game, copies `fantasycore` and `empyrean_campaign` into `mods/`, and writes output under gitignored `emscripten/`.
- `linux/package_steamrt.sh` optionally takes a flare-game path; without it, it packages engine + `mods/default` only.
- `macos/README.txt`: DMG creation scripts live in https://github.com/flareteam/flare-dmg, not here.
- `create_release_tarball.sh` archives `HEAD` as `flare-engine-$(git describe --tags).tar.gz`.
- `windows/itch.toml` defines itch.io play actions for `flare.exe`.

## Work Guidance
Follow the comments at the top of each packaging script for required inputs (flare executable, flare-game path, staging files). `INSTALL.engine.md` documents CMake install prefixes (`BINDIR`, `DATADIR`, `MANDIR`).

## Verification

## Child DOX Index
No child AGENTS.md. `emscripten/`, `linux/`, `macos/`, and `windows/` stay documented here.
