# cmake

## Purpose
CMake find modules so root `CMakeLists.txt` can locate SDL2, SDL2_image, SDL2_mixer, and SDL2_ttf.

## Ownership
- `FindSDL2.cmake`, `FindSDL2_image.cmake`, `FindSDL2_mixer.cmake`, `FindSDL2_ttf.cmake`.
- `Copyright.txt` — license text for these modules (Kitware / Insight Software Consortium / Justin Jacobs; OSI-approved BSD, per the module headers).
- Parent owns `CMakeLists.txt` (`cmake_minimum_required` 3.10, project `Flare`, `VERSION` 1.15, `CMAKE_MODULE_PATH` includes this directory, executable `flare`, install rules).

## Local Contracts
- Configure fails fatally if any of the four SDL2 packages is missing (`Find_Package` + `FATAL_ERROR` in `CMakeLists.txt`).
- These files are find modules, not the build graph. Do not add engine sources here.

## Work Guidance
- Keep modules compatible with the variables `CMakeLists.txt` uses: `SDL2_FOUND` / `SDL2_INCLUDE_DIR` / `SDL2_LIBRARY`, `SDL2IMAGE_*`, `SDL2MIXER_*`, `SDL2TTF_*`, and `SDL2MAIN_LIBRARY`.

## Verification
- Successful `cmake .` from the repository root (requires the SDL2 dev packages listed in `INSTALL.engine.md`). Follow with `make` as in CI.

## Child DOX Index
- No nested AGENTS.md.
