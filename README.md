# NORDIC DLSS5

[Windows installer](https://github.com/gunkobaek/NORDIC-DLSS5/releases/download/v0.7.4-alpha.6/NordicDLSS5.exe) · [Manual add-on ZIP](https://github.com/gunkobaek/NORDIC-DLSS5/releases/download/v0.7.4-alpha.6/NORDIC-DLSS5-Addon-v0.7.4-alpha.6.zip) · [Alpha 6 release](https://github.com/gunkobaek/NORDIC-DLSS5/releases/tag/v0.7.4-alpha.6)

![NORDIC DLSS5 launcher and overlay preview](https://github.com/gunkobaek/NORDIC-DLSS5/releases/download/v0.7.4-alpha.6/NORDIC-DLSS5-Preview.png)

# NORDIC DLSS5 — Alpha 6 / First-launch auto-update fix

Setup **0.5.9** / unchanged Core **0.7.4**.

## Fixed a real first-install update bug

Previously, a downloaded EXE that had not successfully installed a game was not registered as the managed launcher. Its update check could be skipped while the UI incorrectly said **Launcher is up to date**. This meant a failed game/runtime installation could also prevent the user from getting the launcher update automatically.

- Opening this downloaded EXE now installs/opens the managed launcher in your local application data **before any game installation**. No NVIDIA runtime or successful game setup is required to enable launcher auto-update.
- Reopening a matching downloaded EXE forwards to the installed launcher without rewriting it. An older downloaded copy cannot downgrade a newer installed launcher. Close any other Nordic window before manually opening a newer downloaded EXE.
- Skipped checks and disabled automatic updates are distinct from a successful check with no newer release. **Up to date** is shown only after an actual successful GitHub check and includes the release tag.
- The header now shows **SETUP 0.5.9** so testers can identify the launcher version separately from the unchanged Core version.

**If you were stuck running an Alpha 4/5 EXE directly from Downloads after a failed installation, download and open this EXE manually once.** That older standalone EXE cannot acquire this bootstrap correction by itself. Already-installed Alpha 4/5 launchers can receive Alpha 6 automatically, or through **⋯ → Check for updates now**. Automatic startup checks are cached for up to 30 minutes; Check for updates now forces a fresh check.

The runtime discovery and immediate validation improvements from Alpha 5 remain included. Activity log and Open log folder are in the ⋯ menu. A failed runtime preflight intentionally leaves game files untouched, so a detected game may not yet have a Gunko folder.

This launcher fix does **not** add a different NVIDIA runtime or new GPU compatibility. The required original NR runtime remains **nvngx_dlssnr.dll 310.9.16.0**, exact SHA-256:

`2bc19bc09a7b89dd44f73e2ac0108fcc586e2154bdd0830f242f4f040e28789f`

The public EXE and ZIP do not include or download NVIDIA DLLs. A different GPU-specific build is not made compatible by renaming it or editing runtime.ini.

## Validation

25 updater/bootstrap checks, 16 runtime-discovery checks, 71 installer checks and 20 UI/menu checks passed. An actual isolated first launch from a downloaded copy was also checked: it installed and started the managed launcher, with no runtime imported and no game installation started. Existing-game rendering code and tuning defaults are unchanged; this hotfix does not require reinstalling existing add-ons.

**Still alpha—expect bugs.** Windows 10/11 x64, .NET Framework 4.8, unsigned EXE. Both pass defaults remain Bear → Serpent, Serpent at 87%, Present with the pre-FG compatibility route when FG is detected. Open Nordic with backslash. Full ReShade/Reno controls require restarting with FG disabled. Automatic updates affect the launcher; future game add-on updates use Install/Update with the game closed.

[Core 0.7.4 changes, validation and limitations](https://github.com/gunkobaek/NORDIC-DLSS5/releases/tag/v0.7.4-alpha.4)

The NVIDIA runtime/models remain NVIDIA's property. Bear/Falcon/Serpent are style names. NORDIC supplies its experimental integration and UI, not an official NVIDIA SDK integration or endorsement. No LecramDev or ShortFuse add-on or installer is required.

NORDIC focuses on visual quality and performance with two independently tuned passes inside one add-on. The default tuning targets TW3. The author has tested TW3, BG3 and a couple of other AAA titles; this limited set is not a compatibility certification. Almost-daily alpha fixes and more controls are planned.

The combined image is a promotional composition, not a live game capture. This repository distributes alpha binaries and documentation; the integration source is not currently published.
