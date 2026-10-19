# NORDIC DLSS5

> **Known issues under investigation:** with Frame Generation enabled, opening full ReShade using **INS** can freeze TW3. **Use backslash (`\`) to open Nordic only.** Alt+Tab may interrupt NR and Present can flicker. An updated alpha is being tested; these issues are not yet declared fixed. The 0.7.3 launcher has no automatic updater.


[Download the Windows installer](https://github.com/gunkobaek/NORDIC-DLSS5/releases/download/v0.7.3-alpha.3/NordicDLSS5.exe) · [Manual add-on ZIP](https://github.com/gunkobaek/NORDIC-DLSS5/releases/download/v0.7.3-alpha.3/NORDIC-DLSS5-Addon-v0.7.3-alpha.3.zip) · [Alpha 3 release](https://github.com/gunkobaek/NORDIC-DLSS5/releases/tag/v0.7.3-alpha.3)

![NORDIC DLSS5 — launcher and overlay preview](https://github.com/gunkobaek/NORDIC-DLSS5/releases/download/v0.7.3-alpha.3/NORDIC-DLSS5-Preview.png)

An experimental, visual-quality-focused Neural Rendering tool, built around a balance of image quality, performance and a straightforward interface.

NORDIC is designed and optimized around combinations of two independently tuned neural passes inside one add-on. The default stack is **Bear → Serpent**, with both passes enabled at launch and my personal, TW3-focused tuning as the starting point. Bear brings the realistic texture/detail treatment; Serpent adds the cinematic tone. Serpent starts at **87% intensity**. Falcon is also selectable, and either pass can be tuned independently.

**This is an early alpha.** I plan to update it almost daily as development continues, adding new sliders, tuning options, usability improvements and fixes. The interface and defaults may change between builds.

Testing so far is limited to **The Witcher 3, Baldur's Gate 3 and a couple of other AAA titles**. That is a small test set, not a general compatibility guarantee. Results and performance depend on the game, hardware, driver, resolution and settings. My TW3 results are not a promise of the same performance in every title.

## What is included

- A Windows launcher with library scanning, per-game installation/update, Play, backups and restore.
- The original NORDIC integration and compact in-game overlay, using Manrope and opaque charcoal/violet surfaces.
- Bear, Falcon and Serpent runtime styles, two independent passes, collapsible fine tuning and model-resolution controls.
- DirectX 12 support and a built-in DirectX 11 GPU bridge. BG3 must use its DirectX 11 executable. Vulkan is not supported in this alpha.
- Real Rendered / Upscaled / Present processing points. Present is the default, with depth/motion guides Required.
- ReShade 6.8.0 with full add-on support, font assets and notices in the installer. Reno HDR Fix is preserved when already present; it is not included.

## Import the NVIDIA runtime (required)

**The public installer and add-on ZIP do not include or download NVIDIA DLLs.** Obtain your own original `nvngx_dlssnr.dll` from a source authorized to supply it. NORDIC does not link to unverified mirrors.

1. Download and run `NordicDLSS5.exe` from this release; scan your libraries or add the supported game executable.
2. In **Neural runtime**, click **Locate / Change** (the current button reads **Change**) and select your separately obtained `nvngx_dlssnr.dll`.
3. Select the game(s), then click **Install selected** or **Update selected**. Choosing the file alone does not import it: installation verifies the supported version and SHA-256 and imports it into your local shared cache.
4. The supported runtime in this alpha is **310.9.16.0**, SHA-256 `2bc19bc09a7b89dd44f73e2ac0108fcc586e2154bdd0830f242f4f040e28789f`. A different build is rejected; renaming another DLL will not work. This pin is a compatibility check, not a redistribution license or a promise that it is the newest build.
5. Close the game before installation, enable its native DLSS SR/RR path, then start it with Play. A runtime already imported by an earlier NORDIC installation is reused.

## Changes in Alpha 3

- Fix the reproduced TW3 Frame Generation overlay hang: prepare native Manrope glyph sizes and UI geometry buffers during startup, before gameplay. Keep prepared sizes alive without repeating glyph rasterization.
- Avoid an extra submission from Nordic's Present callback; ReShade submits the ordered NR/effects/overlay work at the end of presentation.
- Buttons, toggles and model selectors react on the press edge instead of depending on a later sampled release. Keyboard navigation remains available.
- Keep the earlier non-blocking UI snapshots, safe startup-device rebind and shared/private overlay switching.
- Launch Steam games through Steam, preserve the selected game's persistent highlight, and use physical-pixel button borders.
- Keep Bear + Serpent enabled at startup, Serpent at 87% intensity, Present as the default, and each game's saved tuning.

The previous alpha was withdrawn after the reported TW3 + Frame Generation freeze. Local thread captures identified a synchronous ReShade DX12 font upload on the FG presentation thread. Live TW3 DX12/FG testing of the final build verified repeated Pipeline expansion/collapse, model selection, fine tuning, a saved Local Tone edit and a tooltip while both neural passes continued running. Separate laboratory checks passed for repeated shared/private overlay switching and input polling under engine contention. This is one tested system and game configuration, not general Frame Generation certification.

## Compact interface update

The approved angular N logo uses small plus signs as a mountain ridge and white snow at its feet. The heading is tightly set Manrope vector lettering. Game library rows and Bear/Falcon/Serpent selectors are **50% lower**, while the body font stays readable. Store and renderer details for library rows are available on hover and in the selected-game overview.

## Before testing

Use Windows 10/11 x64, .NET Framework 4.8, a compatible NVIDIA GPU/driver and a supported DLSS SR/RR game path. Close the game before installing. The launcher creates separate backups and preserves existing numeric tuning by default. Existing DLSS game DLLs are not replaced.

Backslash opens the Nordic panel; F10 is the keyboard-layout fallback. Escape closes it. Insert opens shared ReShade. F6 toggles processing, F7 compares and F8 resets history.

**Frame Generation coverage remains limited.** The reported TW3 Present-overlay freeze was retested live; other games, drivers, rendering points and fullscreen/HDR combinations are not certified.

Core 0.7.3 / Setup 0.5.6. The installer is unsigned. Updates currently come from new downloaded builds; no automatic update service is configured.

NORDIC supplies its own integration and UI. The NR networks and runtime are NVIDIA's property; Bear/Falcon/Serpent name their selectable styles, not independently trained NORDIC models. This is unofficial experimental interoperability, not an NVIDIA-endorsed integration. Third-party components retain their own licenses.


The preview is a promotional composition based on the launcher and the isolated overlay laboratory. It is not a live game capture. This repository distributes the alpha binaries and documentation; it does not currently publish the integration source code.
