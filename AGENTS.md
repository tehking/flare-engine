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
- This is tehking's development fork of flare-engine. Do not treat this as the upstream flareteam repo.
- This repository is the C++ FLARE runtime (SDL2, CMake). Default branch is `master`.
- Pair game data lives in tehking/flare-game. Do not document or edit that repository from this work.
- Engine-only: campaign and content mods such as `fantasycore` and `empyrean_campaign` belong in flare-game, not here.

## Child DOX Index
- `src/AGENTS.md` — C++ engine sources (`*.cpp`/`*.h`, platform backends, `Flare.rc`).
- `mods/AGENTS.md` — engine-shipped mods (`default`, `gcw0_defaults`) and `mods.txt`.
- `docs/AGENTS.md` — generated HTML docs and `docs/gen` generators.
- `cmake/AGENTS.md` — CMake FindSDL2* modules used by the root `CMakeLists.txt`.
- `distribution/AGENTS.md` — packaging assets and platform packaging scripts.
- `flare-android-project/AGENTS.md` — Android Gradle/NDK project.
- `flare-ios-project/AGENTS.md` — iOS Xcode project.
- `tools/AGENTS.md` — localization helper scripts.
- `.github/AGENTS.md` — GitHub Actions CI and Dependabot.

Root-owned (no child doc): `CMakeLists.txt`, `README.engine.md` / `README.md`, `INSTALL.engine.md` / `INSTALL.md`, `Codingstyle.txt`, `COPYING`, `CREDITS.engine.txt`, `RELEASE_NOTES.txt`, `.editorconfig`, `astyle_flare.sh`, `extract_xml.sh`, `wiki.xslt`, `regenerate_wiki_attributepage.sh`, `qt.xml`, `fastlane/`, `.tx/`, `.gitattributes`, `.gitignore`, `.gitmodules`.
