# .github

## Purpose
GitHub Actions CI for this fork and Dependabot for Actions versions.

## Ownership
- `workflows/main.yml` — workflow `CI`.
- `dependabot.yml` — weekly `github-actions` updates at `/`.

## Local Contracts
- Triggers: push to `master`, pull_request targeting `master`, `workflow_dispatch`.
- Job `build`: `ubuntu-24.04`, matrix gcc/g++ and clang/clang++, `cmake . && make`. Installs `libsdl2-dev`, `libsdl2-image-dev`, `libsdl2-mixer-dev`, `libsdl2-ttf-dev`, plus EGL/GLES dev packages.
- Job `cppcheck`: `cppcheck --quiet --verbose --enable=all` on `git ls-files src/*.cpp`.
- No Android, iOS, Emscripten, or CTest jobs.

## Work Guidance
- Keep the `build` job matching the desktop path in `INSTALL.engine.md` (`cmake . && make` with the SDL2 dev packages).

## Verification
- The workflow itself is the check: both `build` matrix legs and `cppcheck` must succeed on `master` PRs.

## Child DOX Index
- No nested AGENTS.md.
