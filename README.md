# NORDIC DLSS5

[Windows installer](https://github.com/gunkobaek/NORDIC-DLSS5/releases/download/v0.7.5-alpha.7/NordicDLSS5.exe) · [Manual add-on ZIP](https://github.com/gunkobaek/NORDIC-DLSS5/releases/download/v0.7.5-alpha.7/NORDIC-DLSS5-Addon-v0.7.5-alpha.7.zip) · [Alpha 7 release](https://github.com/gunkobaek/NORDIC-DLSS5/releases/tag/v0.7.5-alpha.7)

![Launcher and overlay preview](https://github.com/gunkobaek/NORDIC-DLSS5/releases/download/v0.7.5-alpha.7/NORDIC-DLSS5-Preview.png)

# NORDIC DLSS5 — Alpha 7 / Experimental FP16 runtime profile

Core **0.7.5** / Setup **0.5.10**.

## Fix for the matching-version runtime rejection

NORDIC previously accepted only the exact original NVIDIA NR binary tested by the author. A user-provided FP16 community variant also reports 310.9.16.0 but has different contents, so both the installer and native add-on rejected it. A failed runtime preflight left game files untouched; a manual installation could not bypass the native check.

This alpha recognizes **two exact user-supplied runtime profiles**, identified by file contents rather than version text:

| Profile | SHA-256 |
|---|---|
| Original NVIDIA 310.9.16.0 (signed) | `2bc19bc09a7b89dd44f73e2ac0108fcc586e2154bdd0830f242f4f040e28789f` |
| Experimental community FP16 compat 310.9.16 | `cdfa6c1ec784867182164c7836f324f087b5c9f374d0c9fe46f54999feabf3ed` |

The second file is the unchanged DLL from the user-supplied RenoDX Discord attachment tagged **compat-fp16-310.9.16-cuda13.4.3**. Its SHA matches the tester's error screenshot. It is **unsigned and community-modified**, not an NVIDIA-signed original or a NORDIC-trained model. The post describes RTX 20/30/40 support; **NORDIC has tested it only on RTX 5090 in isolated laboratories. Older RTX operation remains experimental and requires hardware-specific tester validation.**

- Discovery and Locate recognize either exact profile. FP16 is labeled **experimental** in the launcher.
- The installer imports the selected profile into its own hash-addressed cache and writes its actual path/hash to runtime.ini. Existing NVIDIA game DLLs are preserved.
- The native add-on independently verifies the same two exact hashes. Unknown files remain rejected; version text, renaming or editing runtime.ini cannot override the check.
- Existing users of the original runtime are not automatically switched to FP16. Both profiles use the same Bear/Falcon/Serpent style controls, two-pass stack and saved tuning.
- Includes the Alpha 6 first-launch auto-update correction and visible Setup version. Fresh downloaded EXEs register/open the managed launcher before game/runtime installation.

## How to update and retry

1. Installed Alpha 4 or newer launchers: use **⋯ → Check for updates now**, or allow the startup check. An old standalone EXE that was never installed needs a one-time manual download of this EXE; close other Nordic windows first. The header must show **SETUP 0.5.10**.
2. Close the game. **Updating only the launcher is not enough for this fix.** Select the actual DX11/DX12 game executable and use **Install/Update selected** to install Core 0.7.5.
3. If using FP16 compat, select **Change/Locate** and choose the already-extracted DLL from your own source before installing. Do not choose the RAR archive. Neither runtime is included or downloaded by the public installer.
4. Launch Steam games through Play/Steam with native DLSS SR/RR enabled. Open Nordic with **backslash** (F10 keyboard-layout fallback). For TW3 use DX12; BG3 uses bg3_dx11.exe. Vulkan remains unsupported.
5. On failure, send `Gunko/Gunko.log` from beside the game EXE, Preferences & diagnostics, GPU and driver details. Installer logs are available through **⋯ → Activity log / Open log folder**.

## Validation and limits

Both original and FP16 profiles passed genuine neural two-pass/lifecycle and HDR laboratory tests: three styles, mixed network preset hints, zero-strength identity, resource lifetime, model-resolution rebuild and queue migration. Both passed real DLSS stage tests for Rendered/Upscaled/Present and the FG routing bookkeeping guard. FP16 also passed the DX11 GPU bridge tests, including HDR, 4K output and queued-work stress. These are **RTX 5090 laboratory results**, not game FPS benchmarks or tests on RTX 20/30/40. The updated runtime was not deployed into LIVE games for these tests.

Installer/discovery tests cover distinct profile caches, exact selected-hash configuration, byte-exact import, protected NVIDIA files, rollback and rejection of tampered/unknown files. The native add-on rejects an unknown fingerprint before loading it. Updater and UI/menu regressions are checked as well.

**Still alpha—expect bugs.** The rendering pipeline/tuning behavior is unchanged from Core 0.7.4; new defaults remain Bear → Serpent, Serpent intensity 87%, Local Tone 0.45, Present + Required guides. Updates preserve existing tuning. When FG is detected, Present uses the visible **Upscaled / before FG (Present compatibility)** route; generated presents are not processed twice. Full ReShade/Reno controls require a restart with FG disabled. Existing Reno HDR Fix is preserved, not bundled.

The author's original limited game test set is TW3, BG3 and a couple of other AAA titles. That does not certify this new runtime on those games or other GPUs. Almost-daily fixes and additional controls are planned. Windows 10/11 x64 and .NET Framework 4.8; unsigned installer.

NVIDIA runtime/models and third-party modifications retain their own rights. The provided RAR contained only a DLL, with no redistribution license. **No NVIDIA or community runtime binary is redistributed in this release.** NORDIC's integration/UI and component notices do not grant rights to those binaries. No LecramDev or ShortFuse add-on, installer or bridge is required. This is experimental interoperability, not an official NVIDIA SDK integration or endorsement.

The combined image is a promotional composition based on the existing interface, not a live game capture. This repository distributes alpha binaries and documentation; integration source code is not currently published.
