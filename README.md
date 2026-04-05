# Virtual Desktop Workspace Indicator for Windhawk

A [Windhawk](https://windhawk.net/) mod that displays a visual indicator and vignette effect when switching virtual desktops on Windows 11.

## Features

- **Desktop Indicator** — shows which virtual desktop is active
  - **Numbers style**: `[1] 2 3 4`
  - **Dots style**: `⏺ ○ ○ ○`
- **Vignette Effect** — smooth radial gradient flash on desktop switch
- **Smooth Animations** — eased transitions for indicator and vignette
- **Multi-Monitor Support** — display on all monitors or primary only
- **Fully Configurable** — position, colors, sizes, animation speeds, feather, intensity

## Requirements

- **Windows 11 22H2** or later
- **[Windhawk](https://windhawk.net/)** v1.5+

## Installation

### From Source (Local Mod)

1. Install [Windhawk](https://windhawk.net/)
2. Open Windhawk → click **"Create a new mod"**
3. Copy the contents of `virtual-desktop-indicator.wh.cpp` into the editor
4. Click **Compile Mod** (Ctrl+B), then **Enable**

### From Windhawk Mod Browser

*Coming soon — pending submission to the [official Windhawk mods repository](https://github.com/ramensoftware/windhawk-mods).*

## Settings

| Setting | Default | Description |
|---|---|---|
| Indicator Position | Top Left | Screen corner for the overlay |
| Horizontal Offset | 20 px | Pixel offset from corner |
| Vertical Offset | 12 px | Pixel offset from corner |
| Indicator Style | Dots | Numbers or Dots |
| Indicator Size | 14 px | Font/dot size |
| Active Color | White | Color of the active desktop indicator |
| Inactive Color | Gray | Color of inactive indicators |
| Show Background | Yes | Rounded pill behind indicator |
| Background Opacity | 180 | Pill background opacity (0–255) |
| Always Visible | No | Keep indicator on screen permanently |
| Fade Delay | 2000 ms | How long indicator stays after switching |
| Animation Speed | 200 ms | Highlight slide animation duration |
| Vignette Enabled | Yes | Flash vignette on desktop switch |
| Vignette Color | (0, 220, 120) | Vignette gradient color |
| Vignette Intensity | 150 | Maximum edge opacity (0–255) |
| Vignette Feather | 80 | Gradient softness (0–100) |
| Vignette Animation | 500 ms | Fade in + fade out duration |
| All Monitors | Yes | Show on every monitor |

## How It Works

The mod polls the Windows registry (`HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\VirtualDesktops`) every 20ms to detect virtual desktop changes. When a switch is detected, it triggers indicator animation and vignette flash using GDI+ rendered layered windows.

## License

[MIT](LICENSE)

## Disclaimer

**Use at your own risk.** This mod interacts with internal Windows shell behavior and undocumented registry values. While it does not modify any system files or registry keys (read-only), it runs inside `explorer.exe` via Windhawk's injection framework. The author is not responsible for any issues that may arise from using this software. Always ensure you have a way to disable the mod if something goes wrong (Windhawk's safe mode or disabling the mod from the tray icon).

## Author

**[Disillusion](https://github.com/TheDisillusion)**
