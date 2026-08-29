# docs

## Purpose
Generated HTML documentation for the engine: attribute reference, code conventions, and translations pages.

## Ownership
Owns `docs/*.html` and `docs/gen/` (generator scripts and the attribute-reference preface). Source comments in `src/` and the sibling `flare-engine.wiki` checkout are inputs, not owned here.

## Local Contracts
- `attribute-reference.html` is generated. Preface is `gen/attribute-reference.md`; body comes from root `extract_xml.sh` piped through `wiki.xslt`. Do not treat the HTML as the source of truth.
- `code-conventions.html` and `translations.html` are built only when `../../../flare-engine.wiki` exists next to this repo (`gen/code-conventions.sh`, `gen/translations.sh`).
- `gen/gen_all.sh` runs attribute-reference generation, then the wiki-backed pages.
- Root `regenerate_wiki_attributepage.sh` writes `Attribute-Reference.md` at the repo root (gitignored) for moving onto the wiki.

## Work Guidance
- Edit `gen/attribute-reference.md` for the preface; edit `@CLASS`/`@ATTR`/`@TYPE` comments in `src/` for attribute rows.
- Regenerating wiki-backed pages requires a `flare-engine.wiki` clone beside `flare-engine`.
- Generators expect `markdown` and `xsltproc`.

## Verification

## Child DOX Index
No child AGENTS.md. `gen/` stays documented here.
