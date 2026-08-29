# mods

## Purpose
Engine-shipped mod data: default UI/engine config, translations, fonts, and GCW Zero defaults. Not campaign or game content.

## Ownership
Owns `mods/mods.txt`, `mods/default/`, and `mods/gcw0_defaults/`. Game mods (`fantasycore`, `empyrean_campaign`, and others) live in flare-game and must not be added here.

## Local Contracts
- `mods.txt`: mods lower on the list overwrite data from entries higher on the list.
- `default/` is the engine default mod (menus, `engine/` INI files, fonts, images, cutscenes, gettext catalogs). `default/engine/gameplay.txt` sets `enable_playgame=0`.
- `gcw0_defaults/` holds GCW Zero `settings.txt`, `engine/default_settings.txt`, and `engine/default_keybindings.txt`.
- Data files use the engine’s INI-style key-value format parsed by `src/FileParser`.
- Default mod (including engine translations) is GNU GPL v3 and CC-BY-SA 3.0. Liberation Sans is SIL OFL 1.1. GNU Unifont is GPL v2 with the embedding exception described in `README.engine.md`.
- Transifex resources in `.tx/config` map to `default/languages/data.<lang>.po` and `engine.<lang>.po`.

## Work Guidance
- Keep engine defaults here; put playable campaign data in flare-game.
- Regenerate gettext catalogs with `tools/localization/regenerate_po.sh` (see `tools/AGENTS.md`).
- Language completion tables in `README.engine.md` are produced from Transifex CSV via `tools/localization/transifex_progress.py`.

## Verification

## Child DOX Index
No child AGENTS.md. `default/` and `gcw0_defaults/` stay documented here.
