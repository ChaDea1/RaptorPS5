![Raptor: Call of the Shadows — PS5 port](raptor-banner.png)

# RaptorPS5

**An unofficial native PlayStation 5 port of *Raptor: Call of the Shadows*.**

RaptorPS5 brings the classic DOS shoot-'em-up to PS5 with native DualSense controls, working saves, and two ways to play: **Classic** and **Enhanced**.

Based on [skynettx's SDL2 port](https://github.com/skynettx/raptor), this project is a fan-made tribute to one of my favorite games of all time.

**This is not an official release or a replacement for the commercial game or any future remaster.** No original `.GLB` game data is bundled with the port.

## Classic + Enhanced — v1.0.0-rc.2

The base port is **feature complete** and is now in its second release-candidate stage.

Both modes are playable, with the original campaign, weapons, shop, hangar, and progression intact. Before the stable v1.0.0 release, I'd like to see more community testing across different PS5 setups and complete campaign playthroughs.

### Two ways to play

**Classic Mode**

Experience Raptor with its original presentation, gameplay timing, weapons, balance, and campaign progression.

**Enhanced Mode**

Play the same campaign with smoother 60 FPS rendering, the original gameplay timing, and a widescreen cockpit-style presentation.

Enhanced includes:

- A centered original playfield within a 16:9 display.
- Side HUD panels using original textures, fonts, and weapon artwork.
- Original gameplay boundaries, movement, weapons, balance, and progression.
- Independent pilot saves, separate from Classic.
- Smooth menu refresh while preserving the cadence of original animations.

**Enhanced is a presentation upgrade, not a gameplay rebalance.** The original campaign plays as intended.

## Features

- Native PS5 dashboard application with graceful return to the dashboard.
- DualSense support and customizable weapon controls.
- Full campaign, sector selection, hangar, shop, weapons, and progression.
- Ten independent pilot slots per mode.
- Original music and sound effects.
- Game-styled on-screen keyboard for pilot names and callsigns.
- Updated title menu, separate Classic/Enhanced wordmarks, and refreshed dashboard icon.
- Optional, verified first-launch shareware download.
- Support for personally owned full-game files and episode packs.
- Automatic game-data detection with a startup notification.
- Persistent saves, settings, game data and shareware storage under `/data/RaptorPS5/`, separate from the replaceable app folder.

## Download

**[Download RaptorPS5 from GitHub Releases](https://github.com/ChaDea1/RaptorPS5/releases)**

Current release: **v1.0.0-rc.2**

The release includes the PS5 application package, modified source archive, and SHA-256 checksums.

**Game data is not included.** You can download the free Apogee shareware from within the application or provide your own compatible DOS game files.

## Compatibility

The release has been tested on:

| Component            | Tested configuration                                |
| -------------------- | --------------------------------------------------- |
| PS5 firmware         | 13.42                                               |
| Homebrew environment | kstuff                                              |
| Mounting utility     | ShadowMountPlus v1.7beta4                           |
| Game data            | Shareware, owned full-game files, and episode packs |

Saving and loading have been confirmed with shareware and owned full-game content. Individual extra episodes have also been tested successfully.

Other firmware versions and homebrew configurations have not yet been verified.

## Installation

For a new installation:

1. Download `raptor-ps5-v1.0.0-rc.2.zip` from the Releases page.
2. Extract the archive.
3. Copy the entire `PPSA94002` folder to `/data/homebrew/` on your PS5.
4. Launch **Raptor: Call of the Shadows** from the PS5 dashboard.
5. Choose either **Download free Apogee shareware** or **Use my own game files**.

The shareware download requires an internet connection once. Previously installed matching game data can be used offline.

RaptorPS5 is also available directly from the Prospero Homebrew Store!

**Upgrading from RC1 or an earlier build? Read “Saves and Updating” and migrate your files before using the catalog updater.**

### Using your own full-game files

Copy your compatible DOS `.GLB` files directly into:

`/data/RaptorPS5/content/`

Supported files include `FILE0000.GLB` through `FILE0004.GLB`, along with any additional files supplied with your edition.

- Canonical filenames work in uppercase or lowercase.
- Files must be placed directly in `content/`, not inside nested folders or archives.
- Fully close and restart RaptorPS5 after changing game data.
- Personally supplied game files take priority over downloaded shareware.

See `content/README.txt` in the release package for additional information.

## DualSense Controls

| Button                  | Default action                  |
| ----------------------- | ------------------------------- |
| Left stick / D-pad      | Move                            |
| R2 / Cross              | Fire                            |
| L1 / R1 / Circle        | Cycle special weapons           |
| Square / Triangle       | Megabomb                        |
| Touchpad click          | Pause / resume                  |
| Short Options press     | Abort mission dialog            |
| Hold Options (\~700 ms) | Open / close on-screen keyboard |

### Customizing controls

Open **Controls** from the game's Options menu to reassign Fire, Cycle Weapon, and Megabomb.

Select an action, release Cross, and press the desired face, shoulder, or trigger button.

- Duplicate button assignments are rejected.
- Options cancels button capture.
- Back discards unsaved changes.
- Save and Back stores your assignments.
- Restore Defaults resets the configurable controls.

Movement, menu navigation, and pause/back shortcuts remain fixed for both modes. Custom assignments are shared between Classic and Enhanced and persist across restarts.

### On-screen keyboard

To enter a pilot name or callsign, highlight the field with Cross and hold Options for approximately 700 ms.

| Button   | Keyboard action         |
| -------- | ----------------------- |
| D-pad    | Select key              |
| Cross    | Type selected character |
| Square   | Backspace               |
| Triangle | Enter                   |
| Circle   | Close keyboard          |

Enter or triangle advances the name/callsign dialog and proceeds to difficulty selection when complete.

The keyboard uses the original game's fonts and metal-texture styling.

## Saves and Updating

### Save locations

All writable files now live outside the replaceable application folder, under `/data/RaptorPS5/`.

| Save data              | Location / filename                |
| ---------------------- | ---------------------------------- |
| Classic pilots         | `saves/CHAR0000.FIL` – `CHAR0009.FIL` |
| Enhanced pilots        | `saves/ENH0000.FIL` – `ENH0009.FIL`   |
| Controller assignments | `saves/CONTROLS.CFG`                |
| Game settings          | `SETUP.INI`                         |
| Owned full-game files  | `content/FILE*.GLB`                 |
| Downloaded shareware   | `FILE*.GLB` and `shareware-original.zip` |

Classic and Enhanced each have ten independent pilot slots. Their progress does not overwrite the other mode. Settings, saves and game files remain in `/data/RaptorPS5/` when the catalog replaces the app folder.

### Updating an existing installation

**Before updating RC1 or an earlier release through the PS5 Homebrew Catalog, migrate your files.** The catalog replaces the entire `/data/homebrew/PPSA94002/` folder. Old files left there may be deleted before RC2 can start, and cannot then be imported by the new build.

Fully close Raptor. Back up your existing files, then copy them into the matching persistent locations:

- Old `saves/` (including `CONTROLS.CFG`) → `/data/RaptorPS5/saves/`
- Old `content/` and any owned GLBs → `/data/RaptorPS5/content/`
- `SETUP.INI`, loose `FILE*.GLB` files and `shareware-original.zip` → `/data/RaptorPS5/`

Alternatively, while the old app folder is still intact, replace only `eboot.bin` with the RC2 executable and launch once. The new build imports recognized saves, settings, game files and the retained shareware archive without deleting the originals or overwriting existing persistent files. Verify both modes’ pilots, loading and saving, settings and game data, and keep your backup. Optional legacy mod folders may need to be copied manually.

If the catalog already removed the old app folder, the new app cannot recover files that were left there. After migration, ordinary catalog updates can replace the application folder; **never delete `/data/RaptorPS5/`** if you want to keep your files. New installations can follow the Installation steps above.

## First-Launch Game Data Setup

RaptorPS5 does not distribute original `.GLB` files, shareware ZIPs, DOS executables, or personal pilot data.

The optional shareware installer is initiated by the player and downloads the free shareware package from DOSGames.com over verified HTTPS. The downloaded archive is retained at `/data/RaptorPS5/shareware-original.zip`. Only the two expected `.GLB` files are extracted, after SHA-256 verification, into `/data/RaptorPS5/`.

### Data detection and priority

RaptorPS5 checks for supported game data at startup.

- Personally installed files in `/data/RaptorPS5/content/` take priority over downloaded shareware.
- Legacy game data is checked during migration; the old `/download0/raptor-shareware/` location is ignored.
- A six-second notification identifies detected game data and available sectors.
- Incomplete Outer Regions file pairs are reported.

To return to first-launch setup, remove the installed `.GLB` files from `/data/RaptorPS5/`, `/data/RaptorPS5/content/`, and any other supported data locations, then fully restart the game.

**Do not delete `/data/RaptorPS5/` if you want to preserve your pilots, settings, or game files.**

Keeping `shareware-original.zip` allows verified shareware to be reinstalled without another download, although the ZIP alone does not bypass the setup screen. The download option can reuse the existing archive.

No registered or full-game content is downloaded by the application.

## Release Candidate Status

RaptorPS5 is currently in its second release-candidate stage. The persistent-storage change is new in RC2; the RC2 executable was uploaded to a PS5, but this build still needs runtime verification after launch.

The following have been tested on the developer's PS5 setup:

- Classic and Enhanced gameplay.
- Shareware and personally owned full-game content.
- Individual episode packs.
- Audio playback.
- DualSense controls and remapping.
- On-screen keyboard.
- Pilot creation, saving, and loading.
- Hangar, shop, and level selection.
- Quit to PS5 dashboard.

Previously reported issues involving Ion Scanner display, HUD visibility during pause and level fades, menu pacing, and startup flashing have been addressed.

Original low-frame animation artwork intentionally retains its original cadence.

The original in-game title background has been restored.

**Broader firmware testing and complete campaign playthroughs are still needed before the stable release.**

## Future Plans

The Classic + Enhanced base port is complete. Future development will explore optional enhancements and mods, including:

- New weapons and weapon upgrades.
- Jet upgrades and leveling.
- New Game Plus.
- Additional graphics enhancements.
- Further gameplay expansion.

These features are **planned, not included in v1.0.0-rc.2**.

A general-purpose mod framework is not currently advertised as available. Gameplay-changing additions may require separate save handling.

Base-port updates will continue to prioritize bug fixes, compatibility, and usability.

## Source Code and Building

Each release includes a modified source archive and SHA-256 checksums alongside the PS5 application package.

The source archive contains:

- Raptor port source code.
- Modified PS5 SDL.
- Native application toolkit.
- Supporting hooks.
- Build scripts.

Building requires the public PS5 Payload SDK, LLVM/Clang, CMake, and Make.

**The SDK and compiler are not bundled.** Existing workspace build scripts assume that dependencies have already been prepared locally.

## Licensing

Original upstream license texts, copyright notices, and permissions are retained in the source archive and application package.

| Component                            | License                    |
| ------------------------------------ | -------------------------- |
| Raptor source                        | GPL-2.0-or-later           |
| Native application toolkit           | GPL-3.0-or-later           |
| SDL                                  | zlib                       |
| miniz                                | MIT                        |
| TinySoundFont                        | MIT                        |
| Nuked OPL3 copy in this distribution | GPL-3.0-or-later (elected) |

For Nuked OPL3, this distribution elects GPL-3.0-or-later under Section 3 of the upstream LGPL-2.1 license. The upstream project remains licensed under LGPL-2.1-or-later.

Applicable font copyright and permission notices are preserved.

The binary package and corresponding source archive include notices under `native/licenses/`, including the dated PS5 modification record and source/rebuild guidance.

**Original Raptor game data retains its original rights and is separate from the open-source software licenses. No registered or full-game assets are distributed.**

## Credits and Acknowledgments

RaptorPS5 builds on the work of several developers and open-source projects:

- [skynettx/raptor](https://github.com/skynettx/raptor), based on nukeykt's reverse-engineered Raptor codebase.
- [ps5-payload-dev/SDL](https://github.com/ps5-payload-dev/SDL) and the public PS5 Payload SDK.
- [blackbearreloaded/ps5-native-app-boilerplate](https://github.com/blackbearreloaded/ps5-native-app-boilerplate).
- The original Raptor developers and respective rights holders.

### A personal thank-you

**A MASSIVE thank-you to Scott Host and everyone at Cygnus Studios for creating Raptor: Call of the Shadows!**

I've loved this game since childhood, and I still genuinely believe it's the best shoot-'em-up ever made.

RaptorPS5 exists because I wanted to bring that experience to another platform and share it with other fans.

Banner and dashboard icon artwork were AI-generated. Development was assisted by Codex and ChatGPT.

This is an unofficial, fan-made community project.

## Reporting Issues

If you encounter a problem, please [open a GitHub issue](https://github.com/ChaDea1/RaptorPS5/issues).

Include your PS5 firmware version, kstuff/loader versions, Classic or Enhanced mode, game-data edition (shareware or full game), and steps to reproduce the issue.

Please do not upload copyrighted full-game files, private information, or other sensitive data.

Community testing and bug reports are greatly appreciated, especially full campaign playthroughs and results from different firmware configurations.
