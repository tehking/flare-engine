# DOX framework

- DOX is highly performant AGENTS.md hierarchy installed here
- Agent must follow DOX instructions across any edits

## Core Contract
- AGENTS.md files are binding work contracts for their subtrees
- Work products, source materials, instructions, records, assets, and durable docs must stay understandable from the nearest applicable AGENTS.md plus every parent AGENTS.md above it

## Read Before Editing
1. Read the root AGENTS.md
2. Identify every file or folder you expect to touch
3. Walk from the repository root to each target path
4. Read every AGENTS.md found along each route
5. If a parent AGENTS.md lists a child AGENTS.md whose scope contains the path, read that child and continue from there
6. Use the nearest AGENTS.md as the local contract and parent docs for repo-wide rules
7. If docs conflict, the closer doc controls local work details, but no child doc may weaken DOX
Do not rely on memory. Re-read the applicable DOX chain in the current session before editing.

## Update After Editing
Every meaningful change requires a DOX pass before the task is done. Update the closest owning AGENTS.md when a change affects purpose, scope, ownership, structure, contracts, workflows, inputs/outputs, user preferences, or AGENTS.md index contents. Remove stale text immediately. Small edits that do not change behavior may leave docs unchanged, but the DOX pass still must happen.

## Hierarchy
- Root AGENTS.md is the DOX rail: project-wide instructions, global preferences, durable workflow rules, and the top-level Child DOX Index
- Child AGENTS.md files own domain-specific instructions and their own Child DOX Index
- Each parent explains what its direct children cover and what stays owned by the parent
- The closer a doc is to the work, the more specific and practical it must be

## Child Doc Shape
Create a child AGENTS.md when a folder becomes a durable boundary with its own purpose, rules, responsibilities, workflow, materials, or quality standards. Work Guidance must reflect current project standards; if none yet, leave empty. Verification must reflect an existing check; if none, leave empty.
Default section order: Purpose, Ownership, Local Contracts, Work Guidance, Verification, Child DOX Index

## Style
Keep docs concise, current, and operational. Document stable contracts, not diary entries. Prefer direct bullets with explicit names. Do not duplicate rules. Delete stale notes.

## Closeout
Re-check changed paths, update owning docs and indexes, remove stale text, run existing verification when relevant, report any docs intentionally left unchanged and why.

## User Preferences
- This is tehking's development fork of flare-engine. Pair with tehking/flare-game for Empyrean Campaign data. Do not treat this as the upstream flareteam repo.
- Default branch is `master`.
- This repository is the C++ FLARE runtime only (SDL2, CMake). Campaign/mod gameplay data belongs in flare-game, not here.
- Source license: GNU GPL v3 (`COPYING`). Default mod: GNU GPL v3 and CC-BY-SA 3.0 (`README.engine.md`). Fonts in `mods/default/fonts/` have their own licenses (SIL OFL; Unifont GPL v2 with embedding exception).
- Desktop build: `cmake . && make` from the repo root. Dependencies and OS notes are in `INSTALL.engine.md`.
- Engine C++ conventions live in `Codingstyle.txt` (also generated as `docs/code-conventions.html`). Non-trivial changes must be discussed first; prefer small, single-feature pull requests; keep Windows, macOS, and Linux working; isolate platform-specific code.
- Runtime settings and save paths, command-line flags, and translation status tables are documented in `README.engine.md`.
- Game data uses INI-style files. Maps are authored in Tiled with Flare Tiled Tools (`README.engine.md`).

## Child DOX Index
- `src/AGENTS.md` — C++ engine sources (`src/*.cpp`, `src/*.h`, `Flare.rc`).
- `mods/AGENTS.md` — engine-shipped mods and `mods.txt` load order.
- `docs/AGENTS.md` — HTML engine docs and `docs/gen` rebuild scripts.
- `cmake/AGENTS.md` — `FindSDL2*.cmake` modules used by root `CMakeLists.txt`.
- `distribution/AGENTS.md` — packaging assets and platform release scripts.
- `flare-android-project/AGENTS.md` — Android Studio / NDK wrapper around `src/`.
- `flare-ios-project/AGENTS.md` — Xcode iOS wrapper around `src/`.
- `tools/AGENTS.md` — localization POT/PO helpers.
- `.github/AGENTS.md` — GitHub Actions CI and Dependabot.

Root-owned (no child doc): `CMakeLists.txt`, `README.engine.md` / `README.md`, `INSTALL.engine.md` / `INSTALL.md`, `Codingstyle.txt`, `COPYING`, `CREDITS.engine.txt`, `RELEASE_NOTES.txt`, `astyle_flare.sh`, `extract_xml.sh`, `wiki.xslt`, `regenerate_wiki_attributepage.sh`, `qt.xml`, `.editorconfig`, `.gitignore`, `.gitattributes`, `.gitmodules`, `.mailmap`, `fastlane/` (F-Droid metadata), `.tx/` (Transifex resource map).
