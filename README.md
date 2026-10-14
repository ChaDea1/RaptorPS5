# RaptorPS5

Unofficial native PS5 port of **Raptor: Call of the Shadows**, based on skynettx’s SDL2 port.

## Download

Get the game package from [Releases](https://github.com/ChaDea1/RaptorPS5/releases). **v0.1.0-alpha.1** is an early alpha. Bundled shareware works out of the box; full-game data is not included.

## Compatibility

Tested on PS5 firmware **13.42**, with **kstuff** and **ShadowMountPlus v1.7beta4**. Other firmware versions are untested. Testing confirms startup, video, audio, controls and overlays work with owned full-game data. Saves are working for both the Shareware version and while using the episode packs. Individual extra-episode have also been tested and are confirmed to be working.

## Install

1. Extract `raptor-ps5-v0.1.0-alpha.1.zip`.
2. Copy the complete `PPSA94002` folder to `/data/homebrew/`.
3. Launch **Raptor: Call of the Shadows** from the dashboard.

Close the game before updating. Back up existing pilot saves and configuration before replacing files.

## Full game

Copy your own matching DOS game GLBs (`FILE0000.GLB` through `FILE0004.GLB`, plus any others supplied) directly into `PPSA94002/content/`, or `/data/homebrew/PPSA94002/content/` after installation. Uppercase and lowercase canonical filenames work. Archives, installers and nested folders are not read. See `content/README.txt` in the package. Fully close and restart the game after changing content. Remove custom GLBs to return to shareware.

## DualSense controls

| Control | Action |
| --- | --- |
| Left stick / D-pad | Move |
| R2 / Cross | Fire |
| L1 / R1 / Circle | Cycle special weapons |
| Square / Triangle | Megabomb (requires inventory) |
| Touchpad click | Pause / resume |
| Short Options press | Abort confirmation / Back |
| Hold Options for 700 ms | Toggle keyboard |
| R3 | Toggle controls reference |

Keyboard: D-pad selects a key, Cross presses it, Square sends Backspace, Triangle sends Enter, and Circle closes. Keyboard and controls reference are mutually exclusive. The game continues while overlays are open; use touchpad to pause.

## Source and licensing

The release includes the modified source archive and SHA-256 checksums alongside the binary package. Source archive includes the Raptor port, modified PS5 SDL, native application toolkit, hooks and build scripts. Build requires the public PS5 payload SDK, LLVM/Clang, CMake and Make; the archive does not bundle the compiler or SDK. Existing workspace build scripts assume locally prepared dependencies.

Upstream license texts are retained in the source and game package. Raptor source is GPL-2.0-or-later; the native toolkit is GPL-3.0; SDL uses the zlib license. Original game data retains its original rights and is separate from the source licenses. No registered/full-game assets are distributed.

## Credits

- [skynettx/raptor](https://github.com/skynettx/raptor), based on nukeykt’s reverse-engineered codebase.
- [ps5-payload-dev/SDL](https://github.com/ps5-payload-dev/SDL) and the public PS5 payload SDK.
- [blackbearreloaded/ps5-native-app-boilerplate](https://github.com/blackbearreloaded/ps5-native-app-boilerplate).
- Original Raptor creators and respective rights holders.

Dashboard artwork was AI-generated. This is an unofficial community port.
Created using Codex/ChatGPT. If you don't like that, then I'm sorry i guess? Not really though.

## Reporting problems

Open an issue with firmware, loader versions, reproduction steps, and whether you use bundled shareware or your own full-game data. Do not upload copyrighted full-game data or private information.

## Known Issues

Quit game causes a crash. Graceful exit will be implemented at a later SOON! For now, exit by going to switcher and closing the game, or going to the dashboard and closing it that way.
