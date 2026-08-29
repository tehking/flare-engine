# tools

## Purpose
Maintainer scripts for engine/mod gettext catalogs and the README translation-status table.

## Ownership
- `localization/regenerate_po.sh` — regenerate `engine.pot` (xgettext on `src/*.cpp`, keywords `get` / `getv`) and `data.pot` (`xgettext.py`); optional `-m` merges into `*.po`.
- `localization/xgettext.py` — extracts translatable keys from mod INI files into `data.pot`.
- `localization/transifex_progress.py` — formats a Transifex CSV into the Markdown table used in `README.engine.md`.
- Resource paths for Transifex live in root `.tx/config` (`mods/default/languages/engine.pot` and `data.pot`).

## Local Contracts
- `regenerate_po.sh` must be pointed at a language directory with `-l` (engine usage: `mods/default/languages`).
- `.gitattributes` `export-ignore` entries for `mods/default/languages/regenerate_po.sh` and `xgettext.py` are stale names; the scripts now live in this folder.

## Work Guidance

## Verification

## Child DOX Index
- No nested AGENTS.md. `localization/` stays under this doc.
