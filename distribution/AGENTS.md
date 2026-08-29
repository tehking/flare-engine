# distribution

## Purpose
Packaging and install-time desktop integration for the engine (icons, man page, desktop file, platform release scripts).

## Ownership
- Install inputs referenced by `CMakeLists.txt`: `flare.desktop.in` (configured to build-dir `flare.desktop`), `flare.man` (installed as `man6/flare.6`), `flare_logo_icon.svg` (installed as `flare.svg`).
- Branding: `flare_logo.svg`, `flare_logo_icon.png`, `Flare.ico`, `Flare.bmp`.
- `create_release_tarball.sh` — `git archive` tarball named from `git describe --tags`.
- `nsis_script.nsi` — Windows NSIS installer script.
- `emscripten_template.html` and `emscripten/make_emscripten.sh` — Emscripten build (expects a flare-game path; copies `fantasycore` and `empyrean_campaign` into `mods/`).
- `linux/flare.sh`, `linux/package_steamrt.sh`.
- `macos/package_osx.sh`, `macos/create_iconset.sh`, `macos/README.txt` (DMG scripts live in flareteam/flare-dmg), `macos/docs/`.
- `windows/itch.toml`.

## Local Contracts
- CMake install prefix defaults and `BINDIR` / `DATADIR` / `MANDIR` are set in root `CMakeLists.txt`, not here.
- `create_release_tarball.sh` is `export-ignore` in `.gitattributes`.
- Emscripten output directory `emscripten/` at repo root is gitignored.

## Work Guidance

## Verification

## Child DOX Index
- No nested AGENTS.md. `linux/`, `macos/`, `windows/`, and `emscripten/` stay under this doc.
