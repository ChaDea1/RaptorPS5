![Raptor: Call of the Shadows — PS5 port](raptor-banner.png)

# RaptorPS5

Unofficial native PS5 port of **Raptor: Call of the Shadows**, based on skynettx’s SDL2 port.

## Classic + Enhanced — v1.0.0-rc.1

The base port is **feature complete**. This first release candidate needs wider community testing and complete campaign playthroughs before v1.0.0. Future graphics and gameplay expansions are planned as **optional mods**, rather than additions required to finish Enhanced.

## Port features

- Native PS5 dashboard application with DualSense support and graceful Quit to dashboard.
- **Classic:** original presentation, gameplay, weapons, balance and campaign progression.
- **Enhanced:** smooth 60 FPS rendering with original gameplay timing, the original playfield centered in a 16:9 display, and side HUD panels using original textures, fonts, Megabomb and special-weapon icons.
- Full campaign, sector selection, hangar, shop, original weapons and progression in both modes, using your installed game data.
- Ten independent Classic pilot slots and ten Enhanced slots; mode switching keeps their pilots and progression separate.
- Original music and sound effects, shared audio/detail Options and a game-styled on-screen keyboard for pilot names and callsigns.
- **Controls menu:** remap Fire, Cycle Weapon and Megabomb with PS5 button symbols, explicit Save and Back, and Restore Defaults. Assignments are shared between modes and retained across restarts.
- Enhanced pilot creation/loading, level selection, hangar and shop use the corrected smooth menu refresh; the shared main menu also refreshes at 60 Hz. Original discrete animations retain their own cadence.
- Ion Scanner displays the original-style boss health bar in Enhanced. Enhanced HUD remains visible through pause/abort dialogs and level fades without bringing back Classic HUD elements.
- Original in-game title background and clean menu lettering, separate Classic/Enhanced wordmarks, and a refreshed PS5 dashboard icon.
- Optional verified first-launch shareware download, offline reuse of installed data, owned full-game/episode-pack support, and a startup data-detection notice.
- Optional music-file overrides through the existing mod support.

## Enhanced edition

Enjoy the original campaign with smoother presentation and a wider cockpit-style layout. Enhanced preserves simulation speed, movement boundaries, weapons, balance and progression. Units remain clipped to the original playfield, with shield, credits, Megabombs and special-weapon information alongside the action. Classic remains available from the same title menu with its own saves.

## Release candidate status

The owner has tested Classic and Enhanced with shareware and owned full-game files, including the recent menus, controls and keyboard corrections. Broader console coverage and full campaign playthroughs are still needed. Please report reproducible problems with your firmware, loader versions, selected mode and game-data edition.

Previously listed Ion Scanner, pause/abort HUD, level-fade HUD, menu pacing and startup flashing problems have been addressed. Original low-frame animation artwork is not replaced by the smoother refresh. No PS5 home-menu background or launch artwork is bundled at present; the in-game title background is restored.

## Future mods

The Classic + Enhanced base port is complete. New weapons, weapon/jet leveling, New Game Plus and further graphics changes belong on the optional-mod roadmap. These are plans, not features included in this release or a promise that a general mod framework is already available. Gameplay-changing mods should isolate their saves where needed. Base-port updates will focus on bugs, compatibility and usability.

## Download

Get the game package from [Releases](https://github.com/ChaDea1/RaptorPS5/releases). **v1.0.0-rc.1** is the current release candidate. The package includes no game data. On first launch, download free Apogee shareware or supply your own matching DOS game files.

## Compatibility

Tested on PS5 firmware **13.42**, with **kstuff** and **ShadowMountPlus v1.7beta4**. Other firmware versions are untested. Saves are working for both the Shareware version and while using the episode packs. Individual extra-episodes have also been tested and are confirmed to be fully working.

## Install

1. Extract `raptor-ps5-v1.0.0-rc.1.zip`.
2. Copy the complete `PPSA94002` folder to `/data/homebrew/`.
3. Launch **Raptor: Call of the Shadows** from the dashboard.
4. Choose **Download free Apogee shareware** (Internet required once), or **Use my own game files**. Existing matching data works offline.

Close the game before updating. Back up existing pilot saves and configuration. Update `eboot.bin`, `sce_module/`, `sce_sys/param.json`, `sce_sys/icon0.png` and `licenses/`; retain `saves/`, `content/`, installed GLBs, `shareware-original.zip`, `SETUP.INI` and any personal presentation customizations.

## Full game

Copy your own matching DOS game GLBs (`FILE0000.GLB` through `FILE0004.GLB`, plus any others supplied) directly into `PPSA94002/content/`, or `/data/homebrew/PPSA94002/content/` after installation. Uppercase and lowercase canonical filenames work. Archives, installers and nested folders are not read. See `content/README.txt` in the package. Fully close and restart the game after changing content. Remove custom GLBs to return to downloaded shareware screen, if installed.

## On-screen keyboard

Highlight a pilot name or callsign field with Cross, then **hold Options for about 700 ms** to open the keyboard. D-pad selects a key, Cross types it, Square sends Backspace, Triangle sends Enter, and Circle closes the keyboard. Enter advances the name/callsign dialog and proceeds to difficulty selection when complete. The keyboard uses the original game fonts and metal texture.

## Default DualSense controls

| Control | Action |
| --- | --- |
| Left stick / D-pad | Move |
| R2 / Cross | Fire |
| L1 / R1 / Circle | Cycle special weapons |
| Square / Triangle | Megabomb |
| Touchpad click | Pause / resume |
| Short Options press | Abort mission dialog |
| Hold Options for 700 ms | Toggle keyboard |

Fire, Cycle Weapon and Megabomb can be reassigned in **Controls**. Select an action, release Cross, then press a face, shoulder or trigger button. Buttons already used by another action are rejected. Options cancels capture; Back discards unsaved changes; Save and Back commits them. Movement, menu navigation and pause/back shortcuts stay fixed.

Keyboard: D-pad selects a character, Cross inputs it, Square sends Backspace, Triangle sends Enter, and Circle closes. The game continues while the keyboard is open; use touchpad to pause. The old R3 controls-reference popup has been removed; use the Controls menu for assignments.

## Source and licensing

The release includes the modified source archive and SHA-256 checksums alongside the binary package. Source archive includes the Raptor port, modified PS5 SDL, native application toolkit, hooks and build scripts. Build requires the public PS5 payload SDK, LLVM/Clang, CMake and Make; the archive does not bundle the compiler or SDK. Existing workspace build scripts assume locally prepared dependencies.

Upstream license texts are retained in the source and game package. Raptor source is GPL-2.0-or-later; the native toolkit is GPL-3.0-or-later; SDL uses the zlib license; miniz and TinySoundFont use MIT licenses. This distribution elects GPL-3.0-or-later for its Nuked OPL3 copy under upstream LGPL-2.1 section 3; upstream remains LGPL-2.1-or-later. Font copyright and permission notices are retained. The binary package and corresponding-source archive include the notices in `native/licenses/`, including the dated PS5 modification record and source/rebuild guidance. Original game data retains its original rights and is separate from the source licenses. No registered/full-game assets are distributed.

## Credits

- [skynettx/raptor](https://github.com/skynettx/raptor), based on nukeykt’s reverse-engineered codebase.
- [ps5-payload-dev/SDL](https://github.com/ps5-payload-dev/SDL) and the public PS5 payload SDK.
- [blackbearreloaded/ps5-native-app-boilerplate](https://github.com/blackbearreloaded/ps5-native-app-boilerplate).
- Original Raptor creators and respective rights holders.

Banner and dashboard icon artwork were AI-generated. This is an unofficial community port.
Created using Codex/ChatGPT. If you don't like that, then I'm sorry I guess? Not really though.

## Reporting problems

Open an issue with firmware, loader versions, reproduction steps, and whether you use downloaded shareware or your own full-game data. Never upload copyrighted full-game data or private information.

## Testing status

Core gameplay, shareware and owned full-game episodes, audio, controls, keyboard, saving/loading and Quit to dashboard have been confirmed by the owner on the tested setup. Wider console and firmware coverage is still needed before a stable release.

## Saves and updating

Both shareware and full-game pilots now use `/data/homebrew/PPSA94002/saves/`. The game creates the folder when needed. Classic uses `CHAR0000.FIL` through `CHAR0009.FIL`; Enhanced uses `ENH0000.FIL` through `ENH0009.FIL`. Each mode has ten independent slots. Existing Classic pilots remain Classic pilots. General configuration stays in the base app folder; shared controller assignments are stored in `saves/CONTROLS.CFG`.

When upgrading from alpha:

1. Fully close Raptor and back up existing saves and configuration.
2. Replace `eboot.bin` from the new package. Keep your `content/`, `saves/` (including `CONTROLS.CFG`) and `SETUP.INI`.
3. Copy existing `CHAR0000.FIL` through `CHAR0009.FIL` from the old app root or `content/` into `saves/`. Do not overwrite another pilot; use an unused slot filename if needed.
4. Restart and verify your pilots load. Retain the original files as backups until confirmed.

Updating from beta.4 preserves existing Classic pilots. The update does not automatically migrate old alpha pilot files. See `saves/README.txt` in the package. Quit Game  returns to the dashboard gracefully.

## First-launch data setup

This release distributes no GLBs, shareware ZIP, DOS executables or personal pilots. The optional, player-initiated shareware download comes from DOSGames.com over verified HTTPS. The complete downloaded ZIP is retained as `shareware-original.zip` beside `eboot.bin`; only the two pinned, SHA-256-verified GLBs are extracted into `/data/homebrew/PPSA94002/`. The package does not download registered/full-game content.

Your matching `content/` files take priority over downloaded shareware. Legacy data in `/data/raptor/` also remains supported. The old `/download0/raptor-shareware/` location is ignored. To bring setup back, remove the GLBs from the installed title root, `content/`, and any other supported data folder, then fully close and restart. Keep `saves/` to preserve your pilots. Keeping the original ZIP allows setup to reinstall verified shareware without another network download; the ZIP alone does not skip setup.

A six-second top-left popup reports shareware, the full game, or installed episode packs and lists playable sectors. Outer Regions requires both of its files; an incomplete pair is flagged. Download/install, removal/restart, and popup detection have been confirmed on the tested console.

## Catalog release metadata

Version 1.0.0-rc.1 ships `contentVersion` **00.007.000** and title ID **PPSA94002**. Committed `sce_sys/param.json` and `sce_sys/icon0.png` match the release package. The repository-level LICENSE is GPL-3.0 for the combined native port; individual upstream notices remain in the attached corresponding-source archive. Game data retains its original rights. No game data is included.
