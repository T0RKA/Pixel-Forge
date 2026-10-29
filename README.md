[README.md](https://github.com/user-attachments/files/34106324/README.md)
<div align="center">

# ▦ PIXEL FORGE

### Less detail. More character.

A local-first playground for **dithering, glyph art, color, and motion.**  
Turn an image into something beautifully imperfect—right in your browser.

![HTML](https://img.shields.io/badge/HTML-single_file-d1f587?style=flat-square&labelColor=181b16)
![JavaScript](https://img.shields.io/badge/JavaScript-vanilla-efc58b?style=flat-square&labelColor=181b16)
![Dependencies](https://img.shields.io/badge/dependencies-zero-d1f587?style=flat-square&labelColor=181b16)
![Processing](https://img.shields.io/badge/processing-on_device-efc58b?style=flat-square&labelColor=181b16)

[Features](#features) · [Quick start](#quick-start) · [Motion](#motion-lab) · [Exports](#exports) · [Under the hood](#under-the-hood)

</div>

---

> **Analog spirit. Digital tools.**  
> Crush the gradients. Keep the atmosphere. Trade pixels for symbols. Make it move.

Pixel Forge is a self-contained creative tool built with HTML, CSS, JavaScript, and Canvas. It combines two workspaces—**Dither Studio** and **Glyph Studio**—with a visual palette editor, looping animations, and a reorderable effects stack.

**No accounts. No uploads. No installation. No build step.**

<!-- Optional: add a real screenshot at assets/preview.png, then uncomment the next line. -->
<!-- ![Pixel Forge showing the dithering workspace](assets/preview.png) -->

## Features

| Studio | What you can do |
| :--- | :--- |
| **▦ Dither** | Choose from **10 algorithms**, adjust pixel size from **1–12 px**, and control dither strength from **0–100%**. |
| **Aa Glyph** | Render with **16 character sets** or up to **64 custom Unicode characters**. Adjust cell height from **6–32 px** and character depth from **2–64**, limited by the available characters. |
| **◉ Color** | Start with **7 built-in palettes**, extract **6 colors** from your source, or build a custom palette with **2–16 colors**. |
| **↻ Motion** | Animate still images or video with **7 styles**, playback controls, adjustable speed, and a scrubbable loop timeline. |
| **≋ Effects** | Enable and reorder **5 post-processing effects** with a shared **0–100%** intensity control. |
| **↓ Export** | Save a processed PNG, a real TXT character grid, or a silent WebM animation. |

### The little things matter

- Drag-and-drop image and video import.
- An original generated demo, ready when the app opens.
- Before/after comparison and a **1:1** pixel view.
- Visual color picking for palettes, glyph ink, and glyph backgrounds.
- Single-color, palette-mapped, or source-colored glyphs.
- Optional transparent glyph backgrounds.
- Save and load settings as JSON presets.
- Responsive layouts for desktop and smaller screens.

## Quick start

1. Download [`pixel-forge.html`](pixel-forge.html).
2. Open the file in your browser. **Chrome or Edge is recommended for WebM recording.**
3. Try the generated demo, or click **Import media** to use your own image or video.
4. Choose a studio, pick a look, and start experimenting.
5. Export your artwork.

That is the entire setup. There is no package manager, server, API key, or dependency installation.

> **Private by design:** image processing happens on your device. The application does not upload your media or fetch external libraries, fonts, or artwork. It can run offline; documentation links open external sites only when clicked.

## Two studios. Different kinds of texture.

### 01 / Dither Studio

Turn smooth tones into deliberately imperfect patterns.

| Family | Algorithms |
| :--- | :--- |
| **Error diffusion** | Floyd–Steinberg · Atkinson · Jarvis–Judice–Ninke · Stucki |
| **Ordered** | Bayer **2 × 2** · Bayer **4 × 4** · Bayer **8 × 8** |
| **Pattern & quantization** | Noise dither · Dot halftone · Threshold / nearest color |

### 02 / Glyph Studio

Turn the image into a grid of actual characters—not an ASCII-style overlay.

The **16 built-in sets** cover short ASCII, detailed ASCII, shaded blocks, vertical bars, Braille, dots, squares, circles, runes, medieval ornaments, chess pieces, card suits, digits, binary, arrows, and mathematical symbols.

Prefer something personal? Enter your own text. Custom characters preserve their supplied **dark-to-light order**, and spaces count as characters. Shift the mapping with a **0–63** character offset, or enable animated glyph cycling.

> Glyph appearance depends on the fonts installed on your device. TXT output looks best in a monospaced font.

## Color without the hex codes

The palette editor lives directly inside the app.

1. Click a color swatch.
2. Drag inside the color square to choose saturation and brightness.
3. Move the hue slider to change the color family.
4. Use **Add color** or **Remove** to shape your palette.

The editor also provides saturation and brightness sliders. Switch its target to **Glyph ink** or **Glyph paper** to edit those colors using the same controls.

- Editing a built-in palette creates a custom palette without changing the original preset.
- Custom palettes contain **2–16 colors**.
- In Glyph Studio, palette editing automatically selects palette-mapped character coloring.
- Selecting a paper color turns off the transparent background so the color is visible.

**No hex input required.** Color values are stored internally for preset compatibility.

## Motion lab

Bring a still image to life, or add motion effects to an imported video.

| Animation | Character |
| :--- | :--- |
| **Liquid wave** | Horizontal, flowing distortion |
| **Radial ripple** | Expanding, circular distortion |
| **Breathing zoom** | A gentle push in and pull back |
| **Floating drift** | A looping, floating camera movement |
| **Light pulse** | Rhythmic brightness changes |
| **Color swing** | A looping shift through color |
| **Dither dance** | Changing texture and tonal noise |

### Your controls

- **Play / pause** and **restart**.
- **Timeline scrubbing** to pause on a specific frame.
- **Speed:** **0.25×–3×**, in **0.25×** steps.
- **Intensity:** **0–100%**.
- **Loop length at 1×:** **2, 3, 5, 8, or 10 seconds**.
- Optional glyph-offset cycling alongside the selected animation.

Motion is applied before dithering or glyph rendering, so these are changes to the artwork—not just CSS animations around the preview.

**Recording duration = selected loop length ÷ playback speed.** The record button shows the resulting duration. With no animation enabled, it records **5 seconds** instead.

## Finish the look

Stack and reorder these **5 effects**:

**Scanlines → Film grain → Chromatic shift → Soft glow → Vignette**

The order is editable, and the shared intensity control runs from **0–100%**.

Image adjustments are available before rendering:

| Adjustment | Range |
| :--- | :--- |
| Brightness | **−100 to 100** |
| Contrast | **−80 to 100** |
| Gamma | **0.2–3**, in **0.05** steps |
| Saturation | **0–200%** |
| Invert tones | On / off |

## Exports

| Format | What it saves | Notes |
| :--- | :--- | :--- |
| **PNG** | The processed frame | Exports the processed image even while viewing the original for comparison. Supports transparent glyph backgrounds. |
| **TXT** | The actual character grid | Glyph Studio only. Preserves characters and spacing, not colors or post-processing effects. |
| **WebM** | A silent, real-time recording | Records one animation cycle from its beginning, or **5 seconds** without animation. Requires browser recording support. |
| **JSON** | Your settings and effect order | Does not include source media. Presets are validated as data, not executed as code. |

Output edge options are **640, 960, 1280, or 1920 px**. Source aspect ratio is retained, and smaller sources are never upscaled. Video output is capped at **960 px** for responsiveness.

> Keep the tab visible while recording. A moving video source is not guaranteed to loop seamlessly, even when its applied motion effect does.

## Under the hood

```text
pixel-forge/
├── pixel-forge.html   # Interface, styles, processing, and exports
└── README.md         # You are here
```

**Vanilla HTML + CSS + JavaScript.** Canvas handles image sampling, dithering, glyph rendering, and effects. Browser media APIs handle video playback and WebM capture.

The app intentionally keeps everything in a single file. Open it in a text editor to customize the interface, add palettes, change character sets, or extend the processing pipeline.

### Validation status

**45 automated logic checks** were run during development, covering the dithering algorithms, character grids, palette editing, animation frames and loop boundaries, preset validation, and playback controls.

These checks used mocked browser/canvas objects. They are **not** a substitute for real-browser visual, media-decoding, or recording tests. Live-browser recording and cross-browser behavior remain unverified.

## Current boundaries

Pixel Forge is a lightweight browser tool, not a full desktop editing suite.

- Imported video must use a format and codec that the browser can decode.
- Animated image formats are treated as still images.
- WebM export is silent; audio and GIF export are not implemented.
- No editing timeline, batch conversion, project layers, or SVG export.
- Transparent source pixels are composited onto the first palette color or glyph paper before processing. Transparent glyph output is a separate option.
- Rendering performance depends on resolution, enabled effects, and your device.

## Inspiration & attribution

Inspired by the creative workflows of [Dither Boy](https://studioaaa.com/product/dither-boy/) and [Script Slayer](https://studioaaa.com/script-slayer/) from Studio AAA.

Pixel Forge is an **independent, original implementation**. It is not affiliated with or endorsed by Studio AAA, and it does not include their proprietary code, branding, or artwork.

## License

No license has been selected for this repository yet. Add a `LICENSE` file before specifying permissions for reuse or redistribution.

---

<div align="center">

**Made for pixels with personality.**  
<sub>Less polish. More possibility.</sub>

</div>
