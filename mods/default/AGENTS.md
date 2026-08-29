# mods/default

## Purpose
Fallback engine mod: UI chrome, engine config tables, translations, fonts, and cutscenes required to run the runtime without campaign gameplay.

## Ownership
- `engine/` — engine tables (`classes.txt`, `combat.txt`, `gameplay.txt`, `languages.txt`, fonts, damage types, and the other `engine/*.txt` files in this folder).
- `menus/` — default menu layouts (`config.txt`, `gametitle.txt`, and the other `menus/*.txt` files).
- `languages/` — `engine.pot` / `data.pot` and per-locale `engine.*.po` / `data.*.po`; `credits_settings.txt`.
- `fonts/` — Liberation Sans (SIL OFL) and GNU Unifont.
- `images/` — logos, menu chrome, icons, credits art.
- `cutscenes/` — engine intro/credits cutscenes.
- Translation extraction scripts live under `/tools/localization`, not here. Transifex map is root `.tx/config`.

## Local Contracts
- `engine/gameplay.txt` sets `enable_playgame=0` (this mod is not a playable campaign).
- `engine/languages.txt` tells modders not to overwrite the file; add languages with `APPEND`.
- `README.engine.md`: default mod license is GNU GPL v3 and CC-BY-SA 3.0.
- POT/PO names: `engine.*` from `src/*.cpp` via gettext; `data.*` from mod text via `tools/localization/xgettext.py`.

## Work Guidance

## Verification

## Child DOX Index
- No nested AGENTS.md. Languages, fonts, and images stay under this doc.
