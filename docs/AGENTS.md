# docs

## Purpose
Generated HTML reference for engine attributes, translations, and code conventions.

## Ownership
- Published pages: `attribute-reference.html`, `code-conventions.html`, `translations.html`.
- `gen/` — rebuild scripts and HTML header/footer: `gen_all.sh`, `attribute-reference.sh`, `code-conventions.sh`, `translations.sh`, `header.txt`, `footer.txt`, `attribute-reference.md`.
- Attribute extraction inputs owned at repo root: `extract_xml.sh` (greps `@CLASS` / `@ATTR` / `@TYPE` in `src/*.cpp`), `wiki.xslt`, `regenerate_wiki_attributepage.sh`.

## Local Contracts
- `gen/gen_all.sh` runs `attribute-reference.sh`, then `translations.sh` and `code-conventions.sh`.
- `attribute-reference.sh` writes `docs/attribute-reference.html` from `gen/attribute-reference.md` plus `extract_xml.sh | xsltproc wiki.xslt`.
- `code-conventions.sh` and `translations.sh` only run if a sibling checkout `../../../flare-engine.wiki` exists (they copy `Code-Conventions.md` / `Translations.md`). Without that wiki clone they are no-ops.
- `regenerate_wiki_attributepage.sh` (repo root) writes `Attribute-Reference.md` at the repo root for manual move into the wiki; that output is gitignored.

## Work Guidance

## Verification

## Child DOX Index
- No nested AGENTS.md. `docs/gen/` stays under this doc.
