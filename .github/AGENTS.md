# .github

## Purpose
GitHub Actions CI and Dependabot for this repository.

## Ownership
Owns `workflows/main.yml` and `dependabot.yml`. Build inputs are root `CMakeLists.txt`, `cmake/`, and `src/`.

## Local Contracts
- Workflow `CI` runs on push and pull_request to `master`, and on `workflow_dispatch`.
- Job `build` (ubuntu-24.04, gcc and clang, `fail-fast: false`): install SDL2 dev packages, then `cmake . && make`. A failed build step is turned into a job failure by `Check Status`.
- Job `cppcheck`: `cppcheck --quiet --verbose --enable=all $(git ls-files src/\*.cpp)`.
- Dependabot: weekly `github-actions` updates at `/`.

## Work Guidance
Keep CI package lists aligned with `INSTALL.engine.md` Debian dependencies (`libsdl2-dev`, `libsdl2-image-dev`, `libsdl2-mixer-dev`, `libsdl2-ttf-dev`) plus the EGL/GLES packages the workflow already installs.

## Verification
The workflow itself is the check: both `build` matrix cells and `cppcheck` must succeed on `master` PRs.

## Child DOX Index
No child AGENTS.md.
