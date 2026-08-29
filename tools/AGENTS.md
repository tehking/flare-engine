# tools

## Purpose
Helper scripts for engine and default-mod gettext catalogs, and for README translation-status tables.

## Ownership
Owns `tools/localization/`. PO/POT files live in `mods/default/languages/`. Engine strings live in `src/*.cpp`.

## Local Contracts
- `localization/regenerate_po.sh -l <languages-dir>` regenerates `engine.pot` with `xgettext --keyword=get --keyword=getv` over `src/*.cpp` (forces UTF-8 charset). If `data.pot` exists, it runs `xgettext.py` for mod data. `-m` merges POT into existing `engine.*.po` / `data.*.po`.
- `localization/xgettext.py` extracts translatable strings from mod data into `data.pot`.
- `localization/transifex_progress.py` reads a Transifex CSV and prints the markdown table used in `README.engine.md`.
- Transifex project mapping is root `.tx/config` (`flare-engine` resources `data-pot` and `engine-pot`).

## Work Guidance
Run `regenerate_po.sh` from a context where `-l` points at `mods/default/languages`. Merge with `-m` only when updating existing PO files.

## Verification

## Child DOX Index
No child AGENTS.md.
