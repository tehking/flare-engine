# src

## Purpose
C++ FLARE runtime: game loop, rendering, input, audio, maps, entities, menus, widgets, and INI-style data loading.

## Ownership
Owns all `src/*.cpp` and `src/*.h`, Windows resource `Flare.rc`, and platform backends `Platform*.cpp`. Root `CMakeLists.txt` owns the source-list and compiler flags that consume this tree.

## Local Contracts
- Sources are a flat directory. New `.cpp`/`.h` files must be added to `FLARE_SOURCES` / `FLARE_HEADERS` in root `CMakeLists.txt`.
- Android NDK lists the same units in `flare-android-project/app/src/main/jni/src/Android.mk`; keep that list in sync when adding or removing files.
- `main.cpp` selects one platform backend with preprocessor includes: `PlatformWin32.cpp`, `PlatformAndroid.cpp`, `PlatformIPhoneOS.cpp`, `PlatformGCW0.cpp`, `PlatformEmscripten.cpp`, otherwise `PlatformLinux.cpp`.
- Non-MSVC CMake builds compile with `-std=c++98` and `-fno-exceptions`.
- Mod-file attribute docs are tagged in source with `@CLASS`, `@ATTR`, and `@TYPE` comments consumed by root `extract_xml.sh`.

## Work Guidance
Follow root `Codingstyle.txt`:
- Discuss non-trivial changes (multiple functions or files) before implementing.
- Prefer simple code; OOP only when it clearly beats added complexity. Avoid copy-paste.
- No C++11 / C++0x.
- Isolate platform-specific code; keep Windows, macOS, Linux, and other targets working.
- Tabs (4-space width via `.editorconfig`), Java-style braces on the same line as `if`/`else`/`while`/function.
- Names: `ClassName::functionName`, `ClassName::class_variable`, `local_variable`, `ENUM_OR_CONSTANT`.
- Javadoc-style comments on functions; avoid block comments inside functions.
- Format with root `astyle_flare.sh` (`astyle -S -T4 --style=java -y src/*.[cpp,h]`). Qt Creator can import root `qt.xml`.
- Prefer small pull requests that leave the engine stable.

## Verification
- CI (`.github/workflows/main.yml`): `cmake . && make` with gcc and clang on ubuntu-24.04.
- CI cppcheck: `cppcheck --quiet --verbose --enable=all $(git ls-files src/\*.cpp)`.

## Child DOX Index
No child AGENTS.md. Skip `src/.vscode` (editor settings only).
