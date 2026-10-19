# NORDIC DLSS5

[Windows installer](https://github.com/gunkobaek/NORDIC-DLSS5/releases/download/v0.7.6-alpha.8/NordicDLSS5.exe) · [Manual add-on](https://github.com/gunkobaek/NORDIC-DLSS5/releases/download/v0.7.6-alpha.8/NORDIC-DLSS5-Addon-v0.7.6-alpha.8.zip) · [Alpha 8 release](https://github.com/gunkobaek/NORDIC-DLSS5/releases/tag/v0.7.6-alpha.8)

![Interface preview](https://github.com/gunkobaek/NORDIC-DLSS5/releases/download/v0.7.6-alpha.8/NORDIC-DLSS5-Preview.png)

# NORDIC DLSS5 â€” Alpha 8 / Overlay pointer fix

Core **0.7.6** / Setup **0.5.11**.

Fixes the stale mouse-coordinate override that could make overlay controls stop responding or target the wrong control after input capture/reopening. Nordic now keeps ReShade's viewport-scaled input coordinates intact. The Windows cursor visibility check no longer changes ImGui mouse position.

Validated using the real ReShade DX12 laboratory: six close/reopen cycles with actual Bear/Falcon selections at 0.60x, 1.00x and 1.50x, including a backbuffer/window-size mismatch. Installer rollback/preservation checks and the launcher updater tests passed. This is a targeted alpha fix, not a claim that every TW3/Frame Generation issue is resolved. The user's running TW3 photo session was preserved; this exact patch has not yet been confirmed in that live session.

## Updating

1. In the installed launcher, use **â‹¯ â†’ Check for updates now** (or allow the startup check). The header should show **SETUP 0.5.11**. Old unregistered standalone copies need a one-time manual EXE download.
2. **Close the game**, then select it and use **Install/Update selected** to install **Core 0.7.6**. Updating the EXE alone does not replace an add-on already loaded in a game.
3. Restart the game through Steam/Play. Open Nordic with **backslash** (F10 keyboard-layout fallback).

Existing neural tuning and interface.ini are preserved. New defaults remain Bear + Serpent, both enabled, Serpent intensity 87%, Local Tone 0.45 and Present with Required guides. With Frame Generation detected, Present uses the pre-FG compatibility route. Full ReShade/Reno controls require a session started with FG disabled.

The exact original NVIDIA NR 310.9.16.0 and the experimental community FP16 profile from Alpha 7 remain supported; bring your own extracted runtime. The FP16 variant has been laboratory-tested on RTX 5090 only, with older RTX support unverified. No NVIDIA/community runtime is bundled or downloaded. Vulkan remains unsupported.

Still alpha: expect bugs. Send Gunko/Gunko.log from beside the game EXE, a Preferences & diagnostics screenshot, GPU/driver details and DLSS/FG settings. Setup logs: **â‹¯ â†’ Activity log / Open log folder**. Almost-daily fixes and additional controls are planned.

The combined preview is a promotional composition, not a live game capture. This repository distributes alpha binaries and documentation; integration source is not currently published.
