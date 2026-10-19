# NORDIC DLSS5

[Windows installer](https://github.com/gunkobaek/NORDIC-DLSS5/releases/download/v0.7.4-alpha.5/NordicDLSS5.exe) · [Manual add-on ZIP](https://github.com/gunkobaek/NORDIC-DLSS5/releases/download/v0.7.4-alpha.5/NORDIC-DLSS5-Addon-v0.7.4-alpha.5.zip) · [Alpha 5 release](https://github.com/gunkobaek/NORDIC-DLSS5/releases/tag/v0.7.4-alpha.5)

![NORDIC DLSS5 launcher and overlay preview](https://github.com/gunkobaek/NORDIC-DLSS5/releases/download/v0.7.4-alpha.5/NORDIC-DLSS5-Preview.png)

# NORDIC DLSS5 — Alpha 5 / Runtime detection hotfix

This is a **launcher/installer hotfix**: Setup **0.5.8**, with the exact same Core **0.7.4** add-on as Alpha 4. No game rendering code or tuning defaults changed.

- Runtime discovery now checks contents before showing **Verified**, instead of trusting only the file version. Incompatible files are rejected immediately when selected, with the detected version and checksum in the error.
- Read-only automatic search covers the verified personal cache, a remembered selection, existing Nordic runtime.ini paths, game executable folders, common parent/bin layouts, game subfolders, the launcher folder and local Downloads. Recursive discovery is bounded to three levels, 2,048 folders, 128 candidate DLLs and an approximate 20-second search budget. Use **Locate** for files outside that scope; archives must be extracted first.
- A stale or incompatible automatic candidate no longer hides a compatible file elsewhere. Selecting **Find runtime again** in the ⋯ menu repeats the search.
- Verification runs in the background so the library remains responsive. Install stays disabled until a compatible runtime has been verified; installation still rechecks it before importing.
- **Activity log** shows its file location and can reopen the last installation log after restarting the launcher. **Open log folder** is available in the ⋯ menu, and installation errors show the log path.
- Installed Alpha 4 launchers can receive this hotfix automatically at startup, or through **⋯ → Check for updates now**. Game add-on files are unchanged and do not need reinstalling for this launcher-only fix. Alpha 3/0.7.3 launchers need a one-time manual EXE update.

**This does not add support for a different NVIDIA binary.** The required runtime is still the original nvngx_dlssnr.dll **310.9.16.0** with SHA-256:

`2bc19bc09a7b89dd44f73e2ac0108fcc586e2154bdd0830f242f4f040e28789f`

A different GPU-specific build may not be compatible even if the version label looks the same. Changing runtime.ini's checksum or renaming a DLL does not convert it. If discovery cannot find this exact supported file, use Locate to select your own original runtime from an authorized source. The public EXE/ZIP do not include or download NVIDIA DLLs.

**Still experimental alpha: expect bugs.** This fix was checked with 16 runtime-discovery cases, 71 transactional installer checks, 18 updater checks, 20 launcher/menu checks, setup-progress checks and read-only discovery of the actual required runtime on the author's machine. The unchanged native add-on retains the limited TW3 + Frame Generation validation described in Alpha 4; no new game/GPU compatibility claim is made by this hotfix.

## Core 0.7.4 details and limitations

An experimental Neural Rendering tool focused on visual quality, performance and an interface that is easy to use. NORDIC is designed around **two independently tuned neural passes inside one add-on**. The default stack is **Bear → Serpent**, with my TW3-focused tuning and Serpent at **87% intensity**. Falcon is also selectable in either pass.

**Early alpha: expect bugs.** I plan to update it almost daily with fixes, new sliders and usability improvements. Testing so far is limited to **The Witcher 3, Baldur's Gate 3 and a couple of other AAA titles**. That is the author's small test set, not a compatibility certification. Performance and results vary by game, GPU, driver and settings.

## What changed

- **Present + Frame Generation:** Present remains your saved default. After positively detecting FG, the stack runs after DLSS and before interpolation for the rest of that game session. The overlay explicitly reports **Upscaled / before FG (Present compatibility)**. Generated presents are not processed again. The route stays latched through feature recreation and focus changes instead of switching back to final-frame processing.
- **Present guides:** a newer recorded but unsubmitted DLSS evaluation no longer hides the latest usable submitted depth/motion guides. Required still skips missing guides rather than silently substituting dummy motion.
- **INS protection:** with FG detected, opening full ReShade is intercepted and redirects to Nordic. **Use backslash `\` to open Nordic** (F10 is the keyboard-layout fallback). To use the full ReShade/Reno control panel, restart the game with FG disabled. This is an explicit compatibility workaround, not certification that full ReShade's FG overlay synchronization is repaired.
- **Adaptive overlay:** automatic viewport/DPI sizing plus a native **0.60x–1.50x** manual slider. Fonts, controls and pointer hitboxes scale together. Your manual choice persists separately from neural tuning and survives resolution changes.
- **Independent network preset hints:** each pass can inherit the current preset or request preset 1 or 2 inside Resolution & protection. A real 1+2 stack was tested in the isolated lifecycle laboratory and produced a distinct result from 2+2. Both still use the same verified DLL. Numeric presets are not asserted to identify a documented NVIDIA model revision; separate DLL versions and independent per-pass hook points are not implemented.
- **Optional Safe first launch:** enable it in the installer's Options for a new installation to load the UI in bypass with no NR inference until you explicitly activate Neural rendering or F6. That first activation clears the flag. Existing settings and the usual enabled Bear + Serpent default are preserved.
- **Nordic setup screens:** loading, downloading, verifying and installing share the approved NORDIC logo/icon, condensed wordmark, Manrope and opaque charcoal/violet design. Download percentages use received bytes; installation progress uses verified component writes.
- **Launcher auto-update:** the installed manager checks GitHub Releases at startup, verifies the download against the published SHA-256 and GitHub asset digest, then restarts with the update when idle. The previous launcher is retained for recovery. **0.7.3 users need this one manual update first.** Installed game add-ons are updated with Install/Update while their game is closed; the updater does not replace loaded game DLLs.

## Required NVIDIA neural runtime

**Requires your original `nvngx_dlssnr.dll` version 310.9.16.0 with this exact SHA-256:**

`2bc19bc09a7b89dd44f73e2ac0108fcc586e2154bdd0830f242f4f040e28789f`

This is the runtime validated by this alpha, not a claim that it is the newest NR binary worldwide or compatible with every GPU family. A differently built “40-series” file is not interchangeable just because its version label resembles this one. Editing runtime.ini's checksum does not make an incompatible binary supported.

**The public EXE and ZIP do not include or download NVIDIA DLLs.** Obtain your own original runtime from a source authorized to supply it. NORDIC recommends no unverified mirrors.

1. Close the game and run `NordicDLSS5.exe` from this release.
2. Scan/add the supported DX11 or DX12 game executable. BG3 uses `bg3_dx11.exe`; Vulkan is not supported.
3. In Neural runtime, select **Change/Locate**, choose your original runtime, then **Install/Update selected**. The installer validates and imports it into your personal cache and writes runtime.ini.
4. Launch Steam games through Play or Steam with their native DLSS SR/RR path enabled. **Open Nordic with `\`**, not INS. Both pass switches are on; optional Safe first launch holds the master processing switch off until activation.

The EXE includes ReShade 6.8.0 with full add-on support, NORDIC, its original DX11-to-DX12 GPU bridge, Manrope and notices. Existing Reno HDR Fix is preserved; it is not bundled. Existing NVIDIA game DLLs are preserved. Backups and restore are separate for each game.

New configuration defaults: Bear intensity 1.00 / model resolution 1.00; Serpent intensity 0.87 / model resolution 0.75; Local Tone 0.45 for both; Present + Required guides; Always on off. Updates preserve existing numeric tuning, including different saved resolutions.

## Validation and limits

The isolated laboratories cover genuine NVIDIA neural inference, mixed network hints, all three processing points, submitted/pending guide ordering, temporal reset and queue/resource lifetime. UI fixtures cover native font sizes, 720p–4K viewport containment, DPI, saved manual sizing, fullscreen/focus changes, scaled model selection and the FG INS guard. Installer fixtures cover backup/restore, protected files, DX11 loader selection, optional first-run bypass, update checksums and replacement of a disposable launcher.

The final build is also checked locally in **TW3 DX12 with Frame Generation enabled** before publication. This remains one machine/configuration, not a guarantee for other games, drivers, RTX generations or exclusive fullscreen. The laboratories' synthetic timings are not game FPS or a general temporal-quality assessment. Full ReShade with FG is guarded as described above.

Core **0.7.4** / Setup **0.5.8**. Windows 10/11 x64 and .NET Framework 4.8. The installer is unsigned.

The NVIDIA networks/runtime remain NVIDIA's property. NORDIC supplies its integration and UI; Bear/Falcon/Serpent are style names, not independently trained NORDIC networks. This is unofficial experimental interoperability, not an NVIDIA SDK integration or endorsement. Included components retain their own licenses. No LecramDev or ShortFuse add-on, installer or bridge is required.

The combined preview is a promotional composition, not a live game capture. The repository distributes alpha binaries and documentation; integration source code is not currently published.
