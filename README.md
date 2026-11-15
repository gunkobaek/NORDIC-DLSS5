# NORDIC 5

[Download for Windows (`NordicDLSS5.exe`)](https://github.com/gunkobaek/NORDIC-DLSS5/releases/download/v1.0.7/NordicDLSS5.exe) | [Latest Release (`v1.0.7`)](https://github.com/gunkobaek/NORDIC-DLSS5/releases/tag/v1.0.7)

**Launcher 1.0.7 / Add-on Core 1.0.7**

Light up your game library. Nordic brings up to four independently tuned NVIDIA NR passes, multi-scale local relighting, saved looks and per-game controls to a warm, resizable game launcher and in-game Frost Studio overlay.

## In-Game Add-on & Launcher Preview

### In-Game Frost Studio Add-on (`\` / `F8`) & Skellig Performance HUD (`VRAM GiB`)
![Nordic 5 In-Game Add-on UI and Skellig HUD](docs/screenshots/ingame-addon-ui.png)

### Launcher — Library List View & Selected Game Stage (new interface, 1.0.4)
![Nordic 5 Library — List View](docs/screenshots/library-list.png)

| Library — Grid View | Library — Cinema View |
| :---: | :---: |
| ![Nordic 5 Library — Grid View](docs/screenshots/library-grid.png) | ![Nordic 5 Library — Cinema View](docs/screenshots/library-cinema.png) |

### Profiles, Skellig Performance Monitor & Jata HDR → SDR Capture

| Saved Looks & Multi-Pass Profiles | Skellig Performance Overlay Designer |
| :---: | :---: |
| ![Nordic 5 Profiles](docs/screenshots/profiles.png) | ![Nordic 5 Skellig Overlay Designer](docs/screenshots/skellig-overlay.png) |

![Nordic 5 Jata HDR to SDR Capture](docs/screenshots/jata-capture.png)

### Activity — Update Queue & Session Log
![Nordic 5 Activity](docs/screenshots/activity.png)

## What's new in 1.0.7 & recent releases

**Calibrated Cascadia Mono spacing, readable slider tooltips, D3D12 fullscreen hygiene & optional support link (`v1.0.7`).** Look Inspector slider tooltips now render crisp warm-cream text inside every Prugna Notte tooltip bubble, and all overlay pills, pass cards, `Network Preset` selectors, `Before DLSS` / `After DLSS` / `Present` toggles, footer bars and `Settings` / `Fine-Tune` / `Model Lab` rows measure live `ImGui::CalcTextSize` widths in `Cascadia Mono` without overlap or drag jitter (clearing duplicate `LatinFont=` in `ReShade.ini`). DirectX 12 and Streamline `sl.dlss_g` startup and fullscreen transitions now bypass D3D11 Flow swapchain handlers cleanly, and `Skellig.exe` skips creating a standalone topmost window whenever `Skellig.addon64` is installed alongside `d3d12.dll` / `d3d11.dll` / `dxgi.dll`. The desktop launcher keeps its original warm NJOL interface and theater spotlights while adding a discreet, strictly optional `♥ Support NORDIC 5` footer link (all features remain 100% free). [Full v1.0.7 release notes](https://github.com/gunkobaek/NORDIC-DLSS5/releases/tag/v1.0.7).

**Prugna Notte in-game overlay, enlarged Cascadia Mono, 1–100% pass resolution & fluid DLSS-G UI (`v1.0.6`).** The in-game Frost Studio overlay (`Gunko.addon64`) adopts the deep warm **Prugna Notte** palette (`#1F1421` shell, `#2B1D2D` inspector cards, `#C494F0` lilac-violet accents, `#F5EEF2` cream text) paired with enlarged Microsoft **Cascadia Mono** (`SIL OFL 1.1`, `FontSize=28` in `ReShade.ini`) for crisp technical monospace readability at 1080p, 1440p and 4K, while the desktop launcher keeps its classic warm NJOL dawn interface and theater spotlights untouched. Every neural pass now supports continuous **`1% – 100%`** model resolution scaling across the UI, `settings.ini`, `NeuralCore` and look profiles (preserving aspect ratio down to the 8-pixel-aligned `64 px` floor). Under DLSS Frame Generation 3x/4x, Frost Studio samples the unhooked OS cursor at full display refresh (with a `WM_INPUT` raw-mouse delta fallback when `ClipCursor` pins the pointer), queues temporal history resets atomically and saves `settings.ini` asynchronously off the Present thread. [Full v1.0.6 release notes](https://github.com/gunkobaek/NORDIC-DLSS5/releases/tag/v1.0.6).

**Cleaner neural image, preset-switch fix & Battle.net library (`v1.0.5`).** The glow that outlined relit areas is gone, fringes along strong edges are reduced, and the correction no longer crawls in motion at a model resolution below 1. Measured with the real NVIDIA network on 4K HDR captures of *The Witcher 3*: motion instability about 65% lower, static flicker about 40% lower, edge overshoot about 45% lower, with the same overall look. Changing the network preset or model resolution no longer stalls the neural passes in games that keep two DLSS features alive (*The Witcher 3*: frame rate dropped and only the preset already built kept working). `Gunko.log` is opened once per session, rate limited and trimmed. Render Preset 3 is retired: it was the same network as Preset 2. DirectX 12 games without native DLSS use the color-only Present path without Always On. The launcher scans the Battle.net library (including *World of Warcraft: Forever*) and starts those games through the Battle.net client; online games with anti-cheat carry a warning and install only after you accept it, at your own risk, and may still refuse to load third-party add-ons. Next to `Installed` the launcher now says `not run yet` or `did not load` until a session of that build is recorded. [Full v1.0.5 release notes](https://github.com/gunkobaek/NORDIC-DLSS5/releases/tag/v1.0.5).

**New launcher interface & The Witcher 3 fast-travel flicker mitigation (`v1.0.4`).** One top bar with the NJOL mark, tabs, hover-effect picker and version pill; the Nordic dawn backdrop behind the library; 60 px rows with a status pill (`Installed · verified`, `Update available`), renderer and last session on a second line, white store icons, a floating selection bar and a fluid right-hand stage that never covers the title. The window no longer overflows on long status notices, and the hover title contour follows single-line titles exactly. Core 1.0.4 honors at most four consecutive DLSS `Reset` frames and then keeps its neural temporal history, for games that hold the flag after a loading screen (reported as flicker after fast travel in *The Witcher 3* with in-game Frame Generation). [Full v1.0.4 release notes](https://github.com/gunkobaek/NORDIC-DLSS5/releases/tag/v1.0.4).

**Multi-pass neural rendering & multi-scale local relighting (`v1.0.2`).** Chain up to four independent neural passes (Bear, Falcon, Serpent) with per-pass Intensity, Transfer, Follow Pass 1, Network Preset (`Preset 1 Classic`, `Preset 2 Performance`) and Resolution Scale, paired with multi-scale local tone relighting (`0.00–2.00`), Film Softness (`0.00–1.00`), Cinema/Natural HDR highlight protection, a 31-axis Model Lab in Frost Studio, built-in DirectX 11-to-DirectX 12 GPU bridge and Nordic Flow 2x Frame Generation. [Full v1.0.2 release notes](https://github.com/gunkobaek/NORDIC-DLSS5/releases/tag/v1.0.2).

**Live GPU VRAM (`VRAM GiB`) in Skellig & Unreal Engine 5 fixes.** Skellig's `Clear Minimal` overlay now includes real-time GPU VRAM usage (`used/total GiB` via NVML) alongside FG, FPS, CPU %, CPU GHz, CPU/GPU temperature, system RAM and frametime graph. `Skellig.addon64` stays registered across Unreal Engine 5's temporary DirectX 12 startup probes (fixing missing overlays in games such as *Clair Obscur: Expedition 33*), dynamically reloads target executables and preferences from `session.ini`, and transitions cleanly when `Skellig.exe` runs with administrator permissions for CPU temperature sensors.

**Automatic HDR reference white & screenshots you can hear.** Jata confirms every shot in game with a small "Screenshot saved" note, which never appears in the image, and an optional kantele sound. It now automatically detects and applies RenoDX's *Game Brightness* (`ToneMapGameNits`) in real time on every capture (or matches your Windows HDR display calibration), and can save an optional lossless HDR copy (`.jxr`) next to each PNG.

**Safer updates & library polish.** Nordic asks before updating your games, and *Keep this game on its current Nordic version* stops automatic updates for that game. Library Snow hover banks stay intact across star rating updates. Only one Nordic window runs at a time, and later updates no longer restyle your `ReShade.ini`.

**Under the hood:** smoother neural rebuilds when the resolution changes; logs now show rebuild time, video memory and whether real DLSS depth and motion are used; crash reports are clearer; 32-bit games are reported instead of skipped silently.

## Architecture & File Transparency

Nordic 5 is a self-contained Windows desktop launcher (`NordicDLSS5.exe`) and ReShade Add-on suite (`Gunko.addon64`, `Skellig.addon64`, `Jata.addon64`). It makes **zero background network connections** outside explicit GitHub release update checks and modifies **only** the game directories you explicitly select:

- **`Gunko.addon64` & `Gunko/Gunko.nvngx.dll`**: Intercepts native DLSS inputs (`Color`, `Depth`, `MotionVectors`, `Exposure`) and dispatches the user-supplied signed NVIDIA `nvngx_dlssnr.dll` runtime on DirectX 12 (or via the shared-handle D3D11-to-D3D12 bridge for DirectX 11 games).
- **`Skellig.exe` & `Skellig.addon64`**: Independent hardware-accelerated telemetry overlay powered by Intel PresentMon (MIT) and NVML (`nvml.dll`).
- **`Jata.addon64`**: Clean post-ReShade, pre-UI screenshot capture with PQ/scRGB HDR-to-SDR tone mapping and automatic RenoDX `ToneMapGameNits` detection.
- **Reproducible & Verifiable Release Digests (`v1.0.7`)**:
  - `NordicDLSS5.exe` SHA-256: `5e6e9d50e3e07e6899484cf9788f392eb7b43a68acd6360f1e72b1c8198e4586`
  - `Gunko.addon64` SHA-256: `1ded5fb5829135b5608f508e408653f8adb5be1726340e23cc23962183e3bb74`

## Jata capture (since 0.5.84)

**Jata now supports 64-bit DirectX 9/9Ex, 10/10.1, 11 and 12 games.** Capture the final game image after ReShade effects, without Nordic, ReShade or Skellig panels. The game's own HUD remains. DX11/DX12 HDR scenes are tone-mapped into shareable SDR/sRGB PNGs; DX9/DX10 SDR captures preserve the scene's original colors.

Use **Jata → Enable Jata for this game** for a compatible game without Neural Rendering. The separate capture component does not require an NVIDIA NR runtime. Choose your shortcut, destination folder and HDR reference white; save for one game or all games. Restart the game after installing or updating its addon.

**Scope:** 64-bit executables only; no x86, OpenGL or Vulkan. DX9/DX10 support SDR output, while ambiguous legacy HDR formats are refused. DX9 capture may cause a brief readback hitch at the moment of the shot. Neural Rendering and Skellig's fullscreen renderer retain their own DX11/DX12 requirements. Tested with real DirectX/ReShade fixtures; compatibility is not universal. [Full release notes](https://github.com/gunkobaek/NORDIC-DLSS5/releases/tag/v0.7.32-beta.1).

The release retains integrated CPU temperature, transparent and FPS-only Skellig layouts, the compact graph beside frametime, and the Clair Obscur and repeated neural ON/OFF stability fixes. Personal profiles and tuning are preserved.

## Skellig performance monitor

Skellig runs as a separate app managed from its own launcher tab. Choose Nocturne Strip, Atelier, Instrument, Strip Minimal, Clear Minimal or FPS Only. Clear Minimal has no background and can show a small frametime graph immediately beside the millisecond value. Choose individual metrics including CPU usage, clock, temperature, GPU temperature, **GPU VRAM (`VRAM GiB`)** and system RAM usage. Save design, size and metrics for all games, with position saved separately; individual overrides remain available.

The global ON switch persists and starts Skellig with games launched through Nordic. F9 toggles visibility for the current session. Supports windowed, borderless and exclusive fullscreen in DirectX 11/12. Restart after first enabling fullscreen support or updating its renderer. Layout changes apply at the next Skellig start.

FG measures displayed frames, including generated frames when reported. FPS measures application frames before generation, including with Super Resolution enabled. AVG and the graph use application frames. Unavailable telemetry shows N/D, not a guessed FG multiplier.

CPU temperature is integrated through a bundled CPU-only sensor companion and signed PawnIO driver; no separate monitoring app is needed. Windows permission and occasionally a restart may be required for setup. Sensor availability depends on supported hardware; unavailable readings show N/D.

## Nordic and ReShade shortcuts

INS opens the full ReShade interface. Open Nordic with backslash, its F10 keyboard-layout fallback, or your chosen keybind. Options > Global Nordic Shortcut applies one key to all installed Nordic games and saves the default for new installations. Individual game overrides remain available. Restart running games after changing their shortcut.

## Your library, in a new light

NJOL brown and lavender, the Nordic dawn backdrop, Manrope titles, white store icons, Collector artwork and a disc-style selected-game stage. Each row shows the Nordic status pill, renderer and last session; choose List, Grid or Cinema, save favorites and rate games in half-star steps.

Two warm spotlights sit above the library. Drag horizontally to slide them or diagonally down to aim; the mounts stay on the rail. Lighting > Arrange & aim provides handles, while Power and Drama shape the scene. Spotlight, Cinema and Snow add motion to buttons. Placement, lighting and preferences are saved.

Nordic ON/OFF beside Play controls whether the add-on loads before starting a game. Saved tuning remains available when it is OFF. Profiles, backup/Restore, add-on cleanup and update prompts are built into the launcher.

## Update the launcher and games

Accept Update now in the installed launcher, use Check for updates now, or download and run NordicDLSS5.exe. Keep Nordic open to automatically update add-ons in already installed games. Running games wait until they close. Automatic game updates are enabled by default; a previously saved opt-out is respected. You can also select games and choose Update selected, or use Update all installed game add-ons. Existing profiles, tuning and interface preferences are preserved.

## Render Presets (1 & 2) with the 310.9.16.0 DLL

The current NVIDIA NR `310.9.16.0` DLL offers two **Network Presets**, independent of the Bear, Falcon and Serpent style models:
- **Preset 1 (`Quality / Classic`)**: Runs the legacy `310.8.0` neural graph included for backward compatibility. Uses more GPU compute time (~6.5 ms/pass at 4K 85%).
- **Preset 2 (`Performance / Fast`)**: Runs the newer `310.9.16` Tensor architecture at nearly **2× the speed** of Preset 1 (~3.4 ms/pass at 4K 85%).
- **Preset 3** was retired in 1.0.5: on this runtime it selects the same network as Preset 2 and the image is identical pixel for pixel. A saved Preset 3 loads as Preset 2.

Open Profiles, choose **Gunko_Golden** and Apply to selected games. Applying a profile replaces tuning and creates a backup. The older signed 310.8.0.0 runtime remains available as a separate choice.

Locate your own compatible nvngx_dlssnr.dll in the launcher. No NVIDIA runtime is included or downloaded. Nordic preserves each game's own DLSS SR, Ray Reconstruction, Frame Generation and Streamline DLLs. Restart the game after updating or switching runtime.

## In game and recovery

Backslash opens Nordic; F10 is the keyboard-layout fallback. Escape closes it. F6 toggles processing and F7 compares the image. Set a custom shortcut in Options and restart the game.

Rendered, Upscaled and Present choose where Nordic applies. With Frame Generation active, Present uses the before-FG compatibility route. Healthy means recent NR processing is completing. Waiting, Disabled, Bypassed and GPU error have their own status.

Clean add-ons previews the exact files and saves a backup. Restore recovers the previous files. Games must be closed for updates, cleanup and restoration. Unknown proxy mods and unrelated game files are retained.

## Requirements and feedback

Windows 10/11 x64, .NET Framework 4.8, Microsoft Edge WebView2 Runtime and a compatible NVIDIA NR runtime. Neural Rendering needs native DLSS inputs and a supported DirectX 11 or DirectX 12 executable. Separate Jata capture supports 64-bit DX9/10 SDR and DX11/12 SDR/HDR without requiring the NVIDIA NR runtime. BG3 requires bg3_dx11.exe; Vulkan is unsupported. Compatibility varies by game and GPU.

Report problems through [GitHub Issues](https://github.com/gunkobaek/NORDIC-DLSS5/issues) or your existing tester thread. Include the game, build, GPU/driver and steps to reproduce. Diagnostics exports a support bundle locally; review it before sharing. Nothing is uploaded automatically.

[Made by GUNKO](https://gunko.com/)

