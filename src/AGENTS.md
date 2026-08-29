# src

## Purpose
C++ FLARE runtime: SDL2 game loop, mod data loading, rendering, input, audio, combat, maps, menus, and save/load. This is the engine executable source, not campaign content.

## Ownership
- All `*.cpp` / `*.h` in this folder, plus `Flare.rc` / `resource.h` (Windows executable metadata).
- Platform backends: `Platform.h` and `PlatformWin32.cpp`, `PlatformLinux.cpp`, `PlatformAndroid.cpp`, `PlatformIPhoneOS.cpp`, `PlatformGCW0.cpp`, `PlatformEmscripten.cpp`.
- Parent (`CMakeLists.txt`) owns the desktop source list (`FLARE_SOURCES`, `FLARE_HEADERS`) and link libraries.
- `flare-android-project` owns the NDK source list that compiles these files.

## Local Contracts
- Files are flat; there are no nested source packages. Prefixes group related units:
  - Entry / platform: `main.cpp`, `Platform*`
  - Session / states: `GameSwitcher`, `GameState*`
  - Devices: `DeviceList`, `RenderDevice`, `SDLHardwareRenderDevice`, `SDLSoftwareRenderDevice`, `FontEngine`, `SDLFontEngine`, `SoundManager`, `SDLSoundManager`, `InputState`, `SDLInputState`
  - Mods / config / i18n: `ModManager`, `FileParser`, `EngineSettings`, `Settings`, `MessageEngine`, `GetText`, `Version`
  - World: `Map*`, `TileSet`, `FogOfWar`, `Camera`, `EventManager`, `NPC*`, `Entity*`, `Avatar`, `EnemyGroupManager`, `CampaignManager`, `QuestLog`
  - Combat / items: `StatBlock`, `Stats`, `PowerManager`, `Hazard*`, `EffectManager`, `Loot*`, `Item*`, `XPScaling`, `CombatText`
  - UI: `Menu*`, `Widget*`, `Tooltip*`, `IconManager`, `CursorManager`, `Subtitles`
  - Shared / util: `SharedResources`, `SharedGameResources`, `SaveLoad`, `Animation*`, `AStar*`, `Utils*`
- `FileParser` is the INI-style key-value reader used for mod data.
- `ModManager::FALLBACK_MOD` and `FALLBACK_GAME` are the string `"default"`.
- Render backends registered in `DeviceList.cpp`: `sdl` (software), `sdl_hardware` (default).
- `Platform*.cpp` files are included from `main.cpp` under `#define PLATFORM_CPP_INCLUDE`, not compiled as their own translation units on desktop.
- `src/.vscode/` is local editor config; do not treat it as build input.

## Work Guidance
- Follow `Codingstyle.txt`: C++98 only; no C++11/C++0x; OOP as a last resort; isolate platform-specific code with preprocessor directives.
- Naming: `ClassName::functionName`, `ClassName::class_variable`, `local_variable`, `ENUM_OR_CONSTANT`.
- Tabs (width 4); braces on the same line as `if` / `else` / `while` / the function signature. Javadoc-style comments on functions; avoid block comments inside functions.
- Desktop GNU/Clang flags in root `CMakeLists.txt` include `-std=c++98`, `-fno-exceptions`, and `-Wall -Wextra` (plus the other warning flags listed there).
- New `.cpp`/`.h` files must be added to `CMakeLists.txt` (`FLARE_SOURCES` / `FLARE_HEADERS`) and to `flare-android-project/app/src/main/jni/src/Android.mk` (`LOCAL_SRC_FILES`). `flare-ios-project/FLARE.xcodeproj/project.pbxproj` also lists `../src/*.cpp` individually and is not in lockstep with those two lists.
- Optional format: repo-root `astyle_flare.sh` (`astyle -S -T4 --style=java -y src/*.[cpp,h]`). Qt Creator can import repo-root `qt.xml`. `.editorconfig` matches tab/4 for `*.{cpp,h}`.

## Verification
- Desktop: `cmake . && make` from the repository root (`INSTALL.engine.md`; CI job `build` in `.github/workflows/main.yml`, gcc and clang).
- Static analysis: CI job `cppcheck` runs `cppcheck --quiet --verbose --enable=all` on `git ls-files src/*.cpp`.
- No CTest / `enable_testing` targets exist.

## Child DOX Index
- No nested AGENTS.md. This folder is the local contract for all engine sources.
