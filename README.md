# NORDIC 5

[Download for Windows](https://github.com/gunkobaek/NORDIC-DLSS5/releases/download/v0.7.31-beta.1/NordicDLSS5.exe) | [Latest beta release](https://github.com/gunkobaek/NORDIC-DLSS5/releases/tag/v0.7.31-beta.1)

**Launcher 0.5.83 / Add-on Core 0.7.31**

Light up your game library. Nordic brings two independently tuned NVIDIA NR passes, saved looks and per-game controls to a warm, resizable game launcher.

## What's new in 0.5.83

**Jata brings clean HDR screenshots to Nordic.** Capture directly from your DirectX 12 game, automatically tone-map HDR into shareable SDR/sRGB PNGs, and leave Nordic, ReShade and Skellig panels out of the picture. The game's own HUD remains. Highlight roll-off and color conversion adapt HDR scenes for ordinary screens; SDR captures retain their original range.

Set your own capture shortcut, destination folder and HDR reference white in the **Jata** tab. Save for one game or all games. Match reference white to the game's paper white, restart after updating the addon, and press your shortcut in-game.

This release also adds integrated CPU temperature, transparent and FPS-only Skellig layouts, a compact graph beside frametime, and fixes for Clair Obscur crashes and repeated neural ON/OFF switching. Personal profiles and neural tuning are preserved. [Full release notes](https://github.com/gunkobaek/NORDIC-DLSS5/releases/tag/v0.7.31-beta.1).

## Skellig performance monitor

Skellig runs as a separate app managed from its own launcher tab. Choose Nocturne Strip, Atelier, Instrument, Strip Minimal, Clear Minimal or FPS Only. Clear Minimal has no background and can show a small frametime graph immediately beside the millisecond value. Choose individual metrics including CPU usage, clock, temperature and RAM usage. Save design, size and metrics for all games, with position saved separately; individual overrides remain available.

The global ON switch persists and starts Skellig with games launched through Nordic. F9 toggles visibility for the current session. Supports windowed, borderless and exclusive fullscreen in DirectX 11/12. Restart after first enabling fullscreen support or updating its renderer. Layout changes apply at the next Skellig start.

FG measures displayed frames, including generated frames when reported. FPS measures application frames before generation, including with Super Resolution enabled. AVG and the graph use application frames. Unavailable telemetry shows N/D, not a guessed FG multiplier.

CPU temperature is integrated through a bundled CPU-only sensor companion and signed PawnIO driver; no separate monitoring app is needed. Windows permission and occasionally a restart may be required for setup. Sensor availability depends on supported hardware; unavailable readings show N/D.

## Nordic and ReShade shortcuts

INS opens the full ReShade interface. Open Nordic with backslash, its F10 keyboard-layout fallback, or your chosen keybind. Options > Global Nordic Shortcut applies one key to all installed Nordic games and saves the default for new installations. Individual game overrides remain available. Restart running games after changing their shortcut.

## Your library, in a new light

NJOL brown and lavender, a snowy mountain banner, Lato text, Steam icons, Collector artwork and a DVD-style selected-game display. Choose List, Grid or Cinema, save favorites and rate games in half-star steps.

Two warm spotlights sit above the library. Drag horizontally to slide them or diagonally down to aim; the mounts stay on the rail. Lighting > Arrange & aim provides handles, while Power and Drama shape the scene. Spotlight, Cinema and Snow add motion to buttons. Placement, lighting and preferences are saved.

Nordic ON/OFF beside Play controls whether the add-on loads before starting a game. Saved tuning remains available when it is OFF. Profiles, backup/Restore, add-on cleanup and update prompts are built into the launcher.

## Update the launcher and games

Accept Update now in the installed launcher, use Check for updates now, or download and run NordicDLSS5.exe. Keep Nordic open to automatically update add-ons in already installed games. Running games wait until they close. Automatic game updates are enabled by default; a previously saved opt-out is respected. You can also select games and choose Update selected, or use Update all installed game add-ons. Existing profiles, tuning and interface preferences are preserved.

## Classic quality with the current DLL

The current NVIDIA NR 310.9.16.0 DLL includes the older Classic network under **Render Preset 1**. **Render Preset 2** selects the newer, faster network. These are separate from the Bear, Falcon and Serpent style buttons. Select Preset 1 on both passes for the full Classic look. Classic is the quality-focused option and uses more GPU resources; the preferred look depends on the game and scene.

Open Profiles, choose **Gunko_Golden** and Apply to selected games. The default uses Gunko's TW3 Bear + Serpent tuning with Preset 1 on both passes and the current DLL. Applying a profile replaces tuning and creates a backup. The older signed 310.8.0.0 runtime remains available as a separate choice.

Locate your own compatible nvngx_dlssnr.dll in the launcher. No NVIDIA runtime is included or downloaded. Nordic preserves each game's own DLSS SR, Ray Reconstruction, Frame Generation and Streamline DLLs. Restart the game after updating or switching runtime.

## In game and recovery

Backslash opens Nordic; F10 is the keyboard-layout fallback. Escape closes it. F6 toggles processing and F7 compares the image. Set a custom shortcut in Options and restart the game.

Rendered, Upscaled and Present choose where Nordic applies. With Frame Generation active, Present uses the before-FG compatibility route. Healthy means recent NR processing is completing. Waiting, Disabled, Bypassed and GPU error have their own status.

Clean add-ons previews the exact files and saves a backup. Restore recovers the previous files. Games must be closed for updates, cleanup and restoration. Unknown proxy mods and unrelated game files are retained.

## Requirements and feedback

Windows 10/11 x64, .NET Framework 4.8, Microsoft Edge WebView2 Runtime and a compatible NVIDIA NR runtime. Games need native DLSS inputs and a supported DirectX 11 or DirectX 12 executable. BG3 requires bg3_dx11.exe; Vulkan is unsupported. The beta is unsigned and compatibility varies by game and GPU.

Report problems through [GitHub Issues](https://github.com/gunkobaek/NORDIC-DLSS5/issues) or your existing tester thread. Include the game, build, GPU/driver and steps to reproduce. Diagnostics exports a support bundle locally; review it before sharing. Nothing is uploaded automatically.

[Made by GUNKO](https://gunko.com/)
