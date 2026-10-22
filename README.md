# NORDIC DLSS5

[Download for Windows](https://github.com/gunkobaek/NORDIC-DLSS5/releases/download/v0.7.26-beta.3/NordicDLSS5.exe) | [Latest beta release](https://github.com/gunkobaek/NORDIC-DLSS5/releases/tag/v0.7.26-beta.3) | [Manual add-on](https://github.com/gunkobaek/NORDIC-DLSS5/releases/download/v0.7.26-beta.3/NORDIC-DLSS5-Addon-v0.7.26-beta.3.zip)

**Launcher 0.5.73 / Add-on Core 0.7.26**

Light up your game library. Nordic brings two independently tuned NVIDIA NR passes, saved looks and per-game controls to a warm, resizable game launcher.

## What's new in 0.5.73

- Sort your library by favorites in List, Grid and Cinema views.
- New hand-drawn snow hover with varied adjoining illustrations, preserved proportions and improved ultrawide coverage.
- A fine illuminated outline follows game titles, with gradual fade-in and fade-out across every hover style.
- Faster snow and title animations with smooth transitions.

## Skellig performance monitor

Skellig runs as a separate app managed from its own launcher tab. Choose Compact, Cinema, Instrument, Frost or Bare. Set position and size on the Frost Terminal preview for 16:9, 21:9 or 32:9. Save for one game or share the position and monitor settings across all games while retaining their own design, size and on/off preference.

Enable at game launch or use Start Skellig. F9 toggles visibility while the target game is focused. Supports windowed, borderless and exclusive fullscreen in DX11 and DX12. For fullscreen support, enable Skellig and launch the game from Nordic; restart the game after enabling this support for the first time. Layout changes apply at the next Skellig start. Windows requests administrator permission for FPS capture. FG measures displayed frames, including generated frames when reported. FPS measures application frames before generation, including with Super Resolution enabled. AVG and the frame-time graph use application frames. FPS uses reliable application-frame timing before generation. When that timing is unavailable, FPS, AVG and the graph show N/D rather than an inferred base rate. Availability depends on game/driver telemetry and the installed add-on version. CPU sensors require Libre Hardware Monitor or Open Hardware Monitor with WMI enabled. Missing readings show N/D.

## Nordic and ReShade shortcuts

INS opens the full ReShade interface. Open Nordic with backslash, its F10 keyboard-layout fallback, or your chosen keybind. Options > Global Nordic Shortcut applies one key to all installed Nordic games and saves the default for new installations. Individual game overrides remain available. Restart running games after changing their shortcut.

## Your library, in a new light

NJOL brown and lavender, a snowy mountain banner, Lato text, Steam icons, Collector artwork and a DVD-style selected-game display. Choose List, Grid or Cinema, save favorites and rate games in half-star steps.

Two warm spotlights sit above the library. Drag horizontally to slide them or diagonally down to aim; the mounts stay on the rail. Lighting > Arrange & aim provides handles, while Power and Drama shape the scene. Spotlight, Cinema and Snow add motion to buttons. Placement, lighting and preferences are saved.

Nordic ON/OFF beside Play controls whether the add-on loads before starting a game. Saved tuning remains available when it is OFF. Profiles, backup/Restore, add-on cleanup and update prompts are built into the launcher.

## Update the launcher and games

Accept Update now in the installed launcher, use Check for updates now, or download and run NordicDLSS5.exe. Then close your games, select them and choose Update selected, or use Update all installed game add-ons. Updating the launcher alone does not update the add-on files in games. Ordinary updates preserve existing tuning.

## Classic quality with the current DLL

The current NVIDIA NR 310.9.16.0 DLL includes the older Classic network under **Render Preset 1**. **Render Preset 2** selects the newer, faster network. These are separate from the Bear, Falcon and Serpent style buttons. Select Preset 1 on both passes for the full Classic look. Classic is the quality-focused option and uses more GPU resources; the preferred look depends on the game and scene.

Open Profiles, choose **Gunko / TW3** (`gunko_tw3_old_model`) and Apply to selected games. The default uses Gunko's TW3 Bear + Serpent tuning with Preset 1 on both passes and the current DLL. Applying a profile replaces tuning and creates a backup. The older signed 310.8.0.0 runtime remains available as a separate choice.

Locate your own compatible nvngx_dlssnr.dll in the launcher. No NVIDIA runtime is included or downloaded. Nordic preserves each game's own DLSS SR, Ray Reconstruction, Frame Generation and Streamline DLLs. Restart the game after updating or switching runtime.

## In game and recovery

Backslash opens Nordic; F10 is the keyboard-layout fallback. Escape closes it. F6 toggles processing and F7 compares the image. Set a custom shortcut in Options and restart the game.

Rendered, Upscaled and Present choose where Nordic applies. With Frame Generation active, Present uses the before-FG compatibility route. Healthy means recent NR processing is completing. Waiting, Disabled, Bypassed and GPU error have their own status.

Clean add-ons previews the exact files and saves a backup. Restore recovers the previous files. Games must be closed for updates, cleanup and restoration. Unknown proxy mods and unrelated game files are retained.

## Requirements and feedback

Windows 10/11 x64, .NET Framework 4.8, Microsoft Edge WebView2 Runtime and a compatible NVIDIA NR runtime. Games need native DLSS inputs and a supported DirectX 11 or DirectX 12 executable. BG3 requires bg3_dx11.exe; Vulkan is unsupported. The beta is unsigned and compatibility varies by game and GPU.

Report problems through [GitHub Issues](https://github.com/gunkobaek/NORDIC-DLSS5/issues) or your existing tester thread. Include the game, build, GPU/driver and steps to reproduce. Diagnostics exports a support bundle locally; review it before sharing. Nothing is uploaded automatically.

[Made by GUNKO](https://gunko.com/)
