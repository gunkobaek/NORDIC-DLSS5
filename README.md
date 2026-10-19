# NORDIC DLSS5

[Windows installer](https://github.com/gunkobaek/NORDIC-DLSS5/releases/download/v0.7.7-alpha.10/NordicDLSS5.exe) | [Manual add-on](https://github.com/gunkobaek/NORDIC-DLSS5/releases/download/v0.7.7-alpha.10/NORDIC-DLSS5-Addon-v0.7.7-alpha.10.zip) | [Alpha 10 release](https://github.com/gunkobaek/NORDIC-DLSS5/releases/tag/v0.7.7-alpha.10)

![Interface preview](https://github.com/gunkobaek/NORDIC-DLSS5/releases/download/v0.7.7-alpha.10/NORDIC-DLSS5-Preview.png)

# NORDIC DLSS5 — Alpha 10 / Shortcut persistence

Setup **0.5.13** / Core **0.7.7** (unchanged).

## Fixed in the launcher

- A valid custom overlay shortcut now saves immediately. Closing Options with X no longer discards it; pressing Done is not required for this setting.
- Resetting the shortcut to Default also saves immediately.
- If saving fails, Options reports **Not saved** and retains the previous binding.
- The launcher remembers the last highlighted game on close and restores it on reopening. Rescanning retains the current selection.
- Options names the game's executable beside its shortcut, so per-game settings are easier to identify.

Select a game, open **Options**, click its shortcut and press the new key or combination. **Restart the game** to use the saved binding. Ctrl, Alt and Shift combinations are supported; reserved keys and conflicts with the configured ReShade shortcut remain rejected. Other games retain their own shortcuts.

## Update

Use **… → Check for updates now**, or let the installed launcher's automatic startup check apply the update. Confirm **SETUP 0.5.13**. If you already have Core 0.7.7, no add-on reinstall is needed for this launcher fix. If your game still uses an older core, close it and choose **Install/Update selected**. Updating the EXE alone does not update game add-ons.

Older unregistered standalone copies may require a manual EXE download once.

## Validation and limitations

104 installer/editor/persistence checks and 26 updater checks passed, including Alpha 9 → Alpha 10 release selection. The previously failing close-without-Done regression now passes. The native reader also reads the saved shortcut correctly in a separate process. These are isolated tests, not new live-game or Frame Generation certification.

This release fixes launcher settings persistence. It does **not** claim to resolve the separately reported TW3 hard crash; its cause remains under investigation.

NORDIC remains experimental alpha software focused on visual quality and two-pass tuning. New installs use Bear + Serpent enabled, Serpent intensity 87%, Local Tone 0.45, and Present with Required guides. With FG detected, Present uses the pre-FG compatibility route. Full ReShade/Reno controls require a session started with FG disabled.

Bring your own supported NVIDIA NR runtime: original 310.9.16.0 or the specifically recognized experimental community FP16 profile, verified by exact hash. No NVIDIA/community DLL is bundled or downloaded. Older RTX compatibility remains unverified; Vulkan is unsupported.

For problems, send Gunko/Gunko.log and ReShade.log from the game executable's folder, any crash report/dump, GPU and driver, DLSS/FG settings, and what you did immediately before the failure. Launcher logs: **… → Activity log / Open log folder**.

The combined preview is a promotional composition, not a live game capture. This repository distributes alpha binaries and documentation; integration source is not currently published.
