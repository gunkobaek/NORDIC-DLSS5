# NORDIC DLSS5

[Windows installer](https://github.com/gunkobaek/NORDIC-DLSS5/releases/download/v0.7.7-alpha.9/NordicDLSS5.exe) | [Manual add-on](https://github.com/gunkobaek/NORDIC-DLSS5/releases/download/v0.7.7-alpha.9/NORDIC-DLSS5-Addon-v0.7.7-alpha.9.zip) | [Alpha 9 release](https://github.com/gunkobaek/NORDIC-DLSS5/releases/tag/v0.7.7-alpha.9)

![Interface preview](https://github.com/gunkobaek/NORDIC-DLSS5/releases/download/v0.7.7-alpha.9/NORDIC-DLSS5-Preview.png)

# NORDIC DLSS5 - Alpha 9 / Custom overlay shortcuts

Core **0.7.7** / Setup **0.5.12**.

You can now choose the Nordic overlay shortcut for each game from the launcher:

1. Select the game in the library and open **Options**.
2. Click **Overlay shortcut**, then press a key, optionally with Ctrl, Alt and/or Shift.
3. Click **Done** and restart the game.

**Default** restores backslash. F10 is only the fallback when the active keyboard layout cannot produce backslash without modifiers. Esc still closes Nordic. Reserved Nordic/Windows keys and conflicts with the configured ReShade overlay shortcut are rejected. Choose a shortcut that your game does not use.

The choice is saved per game, separately from neural tuning and UI scale, and survives add-on updates. It can also be set before installing the add-on. Diagnostics display the active shortcut.

## Updating

Use the launcher's **... > Check for updates now**, or its startup update check. Confirm **SETUP 0.5.12**, close the game, and use **Install/Update selected** to install **Core 0.7.7**. Updating the EXE alone does not replace the add-on inside games. Older unregistered standalone launchers may need one manual download.

## Validation and alpha limitations

96 installer/editor/preservation checks and 25 updater checks passed. The C++ reader correctly reads the launcher-written INI and matches launcher key validation. Six synthetic keyboard-event checks through the isolated ReShade DX12 laboratory cover custom opening/closing, the retired default binding and missing modifiers. This is not a new live TW3, exclusive fullscreen or Frame Generation certification.

Includes the Alpha 8 overlay pointer-coordinate fix. Existing tuning is preserved. New installs retain Bear + Serpent enabled, Serpent intensity 87%, Local Tone 0.45, and Present with Required guides. With FG detected, Present uses the pre-FG compatibility route; full ReShade/Reno controls require a session started with FG disabled.

Bring your own supported NVIDIA NR runtime: the original 310.9.16.0 or the explicitly recognized experimental community FP16 profile. These are verified by exact hash, not just version. No NVIDIA/community runtime is bundled or downloaded. The FP16 variant has only been laboratory-tested on RTX 5090; older RTX compatibility remains unverified. Vulkan is unsupported.

Still alpha: expect bugs. Almost-daily fixes and more controls are planned. Reports: send Gunko/Gunko.log beside the game EXE, a Preferences & diagnostics screenshot, GPU/driver and DLSS/FG settings. Installation logs: **... > Activity log / Open log folder**.

The combined preview is a promotional composition, not a live game capture. This repository distributes alpha binaries and documentation; integration source is not currently published.
