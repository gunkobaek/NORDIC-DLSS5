# NORDIC DLSS5

[Windows installer](https://github.com/gunkobaek/NORDIC-DLSS5/releases/download/v0.7.8-alpha.11/NordicDLSS5.exe) · [Manual add-on](https://github.com/gunkobaek/NORDIC-DLSS5/releases/download/v0.7.8-alpha.11/NORDIC-DLSS5-Addon-v0.7.8-alpha.11.zip) · [Alpha 11 release](https://github.com/gunkobaek/NORDIC-DLSS5/releases/tag/v0.7.8-alpha.11)

**Setup 0.5.19 / Core 0.7.8 — experimental alpha.** A personal visual-quality tool built around two independently tuned NVIDIA NR passes. Frequent updates and more controls are planned; expect bugs.

![Nordic launcher interface fixture](https://github.com/gunkobaek/NORDIC-DLSS5/releases/download/v0.7.8-alpha.11/Nordic-Launcher-Preview.png)

## Older NR and the new default

The signed **NVIDIA NR 310.8.0.0** is now supported and has been exercised in **TW3, DirectX 12, with Frame Generation on RTX 5090**, followed by user confirmation. The same native binary recorded about 94,900 submitted frames and 94,887 GPU completions without recorded device loss. Pipeline, model selection, Intensity and Fine Details responded; processing continued after switching away and returning to gameplay. This is bounded validation, not a guarantee that every reported crash is fixed.

New installs use **`gunko_tw3_old_model`**, Gunko's current TW3 tuning: Bear + Serpent, intensity **100% / 79.78%**, resolution scales **90.2248% / 75.4437%**, Present requested and Required guides. It targets the old signed 310.8.0 runtime. Its stronger-looking result is a visual preference, not a measured universal advantage. Other games may need different tuning.

## Profiles and installation

1. Open the launcher and locate your own supported **nvngx_dlssnr.dll**. The default profile requires **310.8.0.0**, SHA-256 `e16bcf15e16e13f527491cdf7845b2fe6521a738d8f7c9c721866a8496e1fc8e`.
2. Check games in the library or use **All**. Choose the game's DirectX executable; native DLSS inputs are required. DX11 uses Nordic's included GPU bridge; Vulkan is unsupported.
3. Open **Profiles**, select `gunko_tw3_old_model`, then **Apply to selected games**. This installs/updates Nordic, replaces tuning and selects the matching locally available runtime for each game. Games must be closed; verified backups and **Restore** are provided.
4. Start through **Play**; Steam games launch through Steam. Open Nordic with **backslash** by default. **F10 is only the keyboard-layout fallback.** Set a custom shortcut in **Options**, then restart the game.

![Look profiles interface fixture](https://github.com/gunkobaek/NORDIC-DLSS5/releases/download/v0.7.8-alpha.11/Nordic-Profiles-Preview.png)

Save current tuning and its runtime fingerprint under your own name, or choose a default for new installs. Close the game before saving. Ordinary updates preserve existing game tuning; explicitly applying a profile replaces it. Hotkeys and UI scale stay per-game. An **edited** label means tuning/runtime differs from the stored profile. Reapply a profile to recover its exact recipe; the overlay's generic Reset tuning is separate.

No NVIDIA/community NR DLL is bundled or downloaded. Nordic verifies exact fingerprints and keeps separate personal caches, preserving the game's DLSS SR/RR, FG and Streamline DLLs. Signed 310.9.16 and the recognized experimental FP16 variant remain available through **Change**. Both passes use the one runtime selected for the Nordic stack. Switching needs install/update and game restart. RTX 20/30/40 compatibility remains unverified here. The exported profile JSON contains tuning and a fingerprint only.

## Other changes

- **Clean add-ons:** exact-file preview, verified external backup and Restore. Unknown proxy mods/game NVIDIA DLLs are retained; nothing is cleaned automatically.
- **Pinned health:** Healthy requires recent GPU-completed NR work. Waiting, Disabled, Bypassed and GPU error have distinct states; Healthy is not a visual-quality guarantee.
- **Controls:** native Intensity 0–1, bounded luminance Fine Details, six neutral-by-default Nordic post-model controls, per-pass numeric render presets. Legacy 310.8.0 ignores the tested preset hints, so its selector is disabled.
- **Launcher:** flat violet selection, Installed subtitles, batch selection, saved custom shortcut, Steam Play, support export, last-session evidence, game-update queue and rollback history.

With FG detected, requested **Present** uses the visible **Upscaled pre-FG compatibility route**. Full ReShade/Reno controls require starting the session with FG disabled. Nordic's private panel is recommended during FG.

## Updating

The installed launcher checks GitHub at startup and every 30 minutes. Accept **Update now** to download, verify and restart, or choose **Later**. Use **… → Check for updates now** manually. Older standalone copies may need one manual EXE download.

Updating the launcher alone does not replace game add-ons or apply a new look to existing tuning. Close games and use **Install/Update selected**, **Update all installed game add-ons**, or opt in to automatic game updates. Keep Nordic open for queued updates; running games wait. Use **Profiles → Apply to selected games** for the new look and old runtime on existing installations.

## Testing and bug reports

Profile/application/rollback, installer, cleanup, discovery, management, updater and UI fixtures passed. Real three-style/two-pass 310.8.0 SDR/HDR, DX11 bridge and UI laboratories passed on RTX 5090; 310.9.16 regression checks passed. See **VALIDATION.json** in the release. This does not establish every game's/GPU's compatibility. Previews are interface/laboratory fixtures, not live captures of named games. This repository distributes binaries and documentation; integration source is not published.

Report via [GitHub Issues](https://github.com/gunkobaek/NORDIC-DLSS5/issues) or your existing tester contact. Include build, GPU/driver, game/renderer, DLSS/FG settings and steps. Send **Gunko/Gunko.log**, **ReShade.log** and crash reports from beside the game executable. Launcher logs: **… → Activity log / Open log folder**. **Diagnostics → Export support bundle** collects local evidence; review before sharing. Nothing is uploaded automatically.
