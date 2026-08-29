# mods

## Purpose
Engine-shipped game data (INI-style mods) loaded at runtime. This repo does not contain Empyrean Campaign or `fantasycore`; those come from flare-game.

## Ownership
- `mods.txt` — active-mod load order for a local/dev tree.
- `default/` — fallback engine mod (`ModManager::FALLBACK_MOD`).
- `gcw0_defaults/` — GCW-Zero default settings and keybindings overlay (`settings.txt` sets `game=default`).
- Parent owns CMake `install(DIRECTORY mods …)` into `DATADIR`.
- User-local override mods live outside this tree (paths in `README.engine.md`).

## Local Contracts
- `mods.txt`: mods lower on the list overwrite data from entries higher on the list. Current entries are `fantasycore` then `empyrean_campaign` (not present in this repo; expected from flare-game).
- The engine always treats `default` as the fallback mod even when it is not listed in `mods.txt`.
- `INSTALL.engine.md`: for a side-by-side engine + game checkout, symlink `mods/default` into the flare-game `mods/` folder (or copy flare-game mods into this `mods/` folder).
- Data format is INI-style key-value files (`README.engine.md`, `src/FileParser.h`).

## Work Guidance

## Verification

## Child DOX Index
- `default/AGENTS.md` — engine fallback mod (menus, engine tables, languages, fonts, images, cutscenes).

Parent-owned here: `mods.txt`, `gcw0_defaults/` (`settings.txt`, `engine/default_settings.txt`, `engine/default_keybindings.txt`).
