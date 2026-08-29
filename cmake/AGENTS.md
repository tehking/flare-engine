# cmake

## Purpose
CMake find modules that locate SDL2, SDL2_image, SDL2_mixer, and SDL2_ttf for the root build.

## Ownership
Owns `FindSDL2.cmake`, `FindSDL2_image.cmake`, `FindSDL2_mixer.cmake`, `FindSDL2_ttf.cmake`, and `Copyright.txt`. Root `CMakeLists.txt` owns project version, compiler flags, source lists, install rules, and `CMAKE_MODULE_PATH`.

## Local Contracts
- Root `CMakeLists.txt` appends this directory to `CMAKE_MODULE_PATH`.
- The four Find modules set `SDL2*_FOUND`, include dirs, and library variables consumed by `CMakeLists.txt`. Missing SDL2 packages fail configure with Debian package hints.
- `Copyright.txt` is the Kitware/BSD license covering these find modules (modified from CMake’s FindSDL).

## Work Guidance
Keep find-module behavior aligned with how `CMakeLists.txt` calls `Find_Package(SDL2)`, `Find_Package(SDL2_image)`, `Find_Package(SDL2_mixer)`, and `Find_Package(SDL2_ttf)`.

## Verification
CI job `build` runs `cmake . && make` (gcc and clang), which exercises these modules.

## Child DOX Index
No child AGENTS.md.
