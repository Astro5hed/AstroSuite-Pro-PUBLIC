# AstroSuite Pro

**Version 1.0.4** — a Windows desktop application for astrophotography stacking and post-processing.

AstroSuite Pro wraps the [Siril](https://siril.org/) command-line engine for calibration and stacking, and adds a large native image-processing toolset built directly into its own image editor.

> Previously released as **AstroStacker Pro**. Renamed at 1.0.4 - it does considerably more than stack now. Settings saved under the old name are carried across automatically the first time you run it.

<img width="3840" height="2100" alt="Screenshot1" src="https://github.com/user-attachments/assets/62991057-4a7f-4bc6-95e8-7647c24ba1aa" />
<img width="3840" height="2100" alt="Screenshot2" src="https://github.com/user-attachments/assets/f4111319-1ee3-40e3-afdc-2d660fb38954" />

---

## Contents

- [Features](#features)
- [Interface](#interface)
- [Stacking](#stacking)
- [Image Editor](#image-Editor)
- [Tools](#tools)
  - [Masking](#masking)
  - [Image Prep](#image-prep)
  - [Calibration & Astrometry](#calibration--astrometry)
  - [Noise, Gradients & Stars](#noise-gradients--stars)
  - [Tone & Stretch](#tone--stretch)
  - [Colour](#colour)
- [Mono support](#mono-support)
- [Requirements](#requirements)
- [Credits](#credits)

---

## Features

- **Full stacking pipeline** driven by a bundled, portable Siril CLI — no separate Siril install required
- **30+ native processing tools**, grouped into a categorised sidebar
- **App-wide masking system** — any mask can be made Active and it applies to *every* tool's result automatically
- **Live preview on every native tool** — background-threaded, debounced, with full-resolution Apply always kept separate from the preview
- **Peak-preserving preview downscaling** so preview results match the applied result even on near-saturated star cores
- **Undo / Redo** across the whole editing chain
- **Compare Viewer** — an independent second window with its own zoom and screen stretch for side-by-side checking
- **Mini Viewer** for quick inspection
- **Files Viewer** tab with a frame list for the current project
- **Drag-and-drop** image loading into the main viewer and Mini Viewer
- **Interactive canvas editing** — draw directly on the image for cropping and blemish repair
- Iterative tools commit silently and reload from the new baseline; one-shot tools offer Save As New / Overwrite / Keep Editing

---

## Interface

- **Menu bar and icon toolbar** across the top - File, Edit, Tools, Settings, Help and About, with a single row of drawn icons for the actions used most
- **Collapsible left panel** with two views, chosen from vertical tabs on the window's edge:
  - **Stacking** - frame types, core parameters, output settings and profiles
  - **History** - every tool applied to the current image, in order. Click any step to return to how the image looked at that point. Earlier sessions on the same image are kept in a permanent log, so months later you can see what you did and when
- **Information Panel and Console** can be hidden together, giving their height to the image
- **Hover tooltips** - a short bubble under the pointer after a pause, with the full description in the Information Panel. Toolbar icons show their name; everything else shows a one-line summary. Switchable off under Settings
- **Before / after compare** on the Editor toolbar - one click shows the image as it was before any editing, another returns
- **Timing summary** after every stacking run: each step with its duration, frame count and share of the total, so a slow run can be compared against a previous one rather than guessed at
- **Offline star catalogue** (optional, ~1.1 GB) for plate solving, so it no longer depends on a remote server

---

## Stacking

- Bundled portable Siril CLI (static copy — no self-update)
- Automatic dark-frame matching across every valid temperature group
- Per-filter handling for multi-filter sessions, with mixed exposure lengths calibrated separately and merged before registration
- **All five of Siril's stacking methods and all eight rejection types**, verified against the bundled Siril's own documented options
- Full control over normalisation, weighting, rejection maps, drizzle and frame filtering
- Master light output loads straight into the image viewer for processing

---

## Image Editor

Full-featured viewer at the centre of the app: zoom, pan, screen-transfer-function display stretch, embedded toolbar, and a preview region system so heavy tools can be tuned on a chosen area.

Two preview conventions are used deliberately, depending on what you're judging:

- **Image Editor previews** for pixel-judgement tools (stretches, curves, star operations) — you need zoom for these
- **In-dialog preview canvases** (560×420) for structure- and mask-judgement tools (RangeSelection Mask, Dust Lane Enhancer, Dark Structure Enhance) — these are judged at overview scale, and leaving the main viewer untouched lets you compare against the original side by side

---

## Tools

### Masking

| Tool | Description |
|---|---|
| **RangeSelection Mask** | Faithful port of PixInsight's RangeSelection, built from the published specification. All eight real parameters: Lower/Upper limit, Link range limits, Fuzziness, Smoothness, Screening, Lightness, Invert. Has its own dedicated mask-preview canvas, plus a Hide/Unhide translucent red overlay on the main image. **Checking "Active" applies the mask to any other tool's result app-wide** — white is fully processed, black is fully protected. |

### Image Prep

| Tool | Description |
|---|---|
| **View FITS Header** | Inspect the full FITS header of the loaded image |
| **Bin / Downscale** | Reduce image dimensions |
| **Set Preview Region** | Restrict live previews to a chosen region for speed |
| **Crop Tool** | Interactive — click-drag a rectangle directly on the viewer, then drag edges and handles to fine-tune |
| **Blemish Blaster** ⭐ | Port of Franklin Marek's BlemishBlaster. Drag on the main viewer to mark hot pixels, dust donuts or small artifacts. The repair samples six donor regions at 60° intervals around each spot, picks the three whose median brightness best matches the spot's surroundings, then samples the same relative offset within each for every repaired pixel — preserving local texture instead of flattening to a single value. Feather and Opacity controls; Undo Last Spot / Clear All Spots. |

### Calibration & Astrometry

| Tool | Description |
|---|---|
| **Background Neutralization** | Neutralise a colour cast in the sky background |
| **LinearFit** | PixInsight's real algorithm — robust IRLS line fit between a reference and target image |
| **Image Solver** | Plate solving |
| **SPCC** | Spectrophotometric colour calibration |

### Noise, Gradients & Stars

| Tool | Description |
|---|---|
| **GraXpert** | Gradient removal and denoising via GraXpert |
| **Background Extraction** | Siril-driven background extraction |
| **Xterminator Tools** | BlurXTerminator, StarXTerminator and NoiseXTerminator through the RC-Astro CLI, driven by its own JSON schema |
| **Star Reduction** | Verified port of Bill Blanshan's PixelMath, with all three real methods (Transfer / Halo / Star). Runs its live preview on true full-resolution data, because the formula depends heavily on exact brightness near 1.0 |
| **Screen Stars** | Bill Blanshan / Mike Cranfield's ScreenStars formula — the exact inverse of unscreen |
| **Star Stretch** ⭐ | Port of Franklin Marek's star_stretch_v2.1. Real hyperbolic curve, plus the script's fixed hue/saturation curve via a native Akima interpolation (verified to match SciPy's own implementation exactly). Stretch Amount and Color Boost sliders, with real SCNR settings |
| **NB to RGB Stars** ⭐ | Port of Franklin Marek's NBtoRGBStars v1.6. Real R/G/B combine formulas followed by the real SCNR → MTF → SCNR → MTF sequence. Takes either three mono narrowband images or a single OSC (dual-band) image, extracting Ha and OIII from its own channels. Adjustable Ha/OIII ratio and an optional final Star Stretch pass |
| **Dust Lane Enhancer** ⭐ | Original tool with no equivalent in other astro software. Applies Frangi vesselness — a medical blood-vessel detection algorithm — to dust lanes and dark filaments, which share the same mathematical shape (elongated ridges rather than blobs). Ported from scikit-image's source and verified to machine precision, then adapted for astro use with Lindeberg scale normalisation and noise-relative sensitivity. Darkening-only by construction, so stars and sky are left untouched and hue is preserved. Includes a Show Detection Map view. **Best on starless images** (post-StarXTerminator / StarNet); on star fields, keeping Smallest and Largest Structure low and close together works well |
| **Dark Structure Enhance** ⭐ | Faithful step-for-step port of DarkStructureEnhance v1.1 (Carlos Sonnenstein & Oriol Lehmkuhl, PTeam). Builds a star-free wavelet base, derives a mask where dark structures are bright and stars clip to zero, then applies an iterated histogram transformation through that mask. Layers, Amount and Iterations controls plus a Show Mask option. Companion to the Dust Lane Enhancer — this one targets dark structure generally, the other targets filaments by shape |

### Tone & Stretch

| Tool | Description |
|---|---|
| **Narrowband Normalization** | Port of Bill Blanshan / Mike Cranfield's NarrowbandNormalization process |
| **Simple Stretch** | Quick non-linear stretch |
| **GHS** (Generalised Hyperbolic Stretch) | Built from the published specification (David Payne / Mike Cranfield, GPL v3) and cross-verified against the official PixInsight reference documentation |
| **Curves** | Native point-based curve editor using monotone cubic Hermite interpolation. Modes: Full RGB, Individual RGB, Luminance Only, Saturation |
| **VeraLux HyperMetric Stretch** | Numerically verified port of Riccardo Paterniti's Siril script |
| **Camera RAW Editor** | Exposure, Highlights, Shadows, Whites, Blacks (smoothstep masking), Vibrance, Clarity, Texture, and Sharpen with radius and detail — sign conventions confirmed against real Lightroom / ACR behaviour |

### Colour

| Tool | Description |
|---|---|
| **Astro Color Mixer** | Multi-band hue / saturation / luminance mixing |
| **Combine RGB / LRGB** | Combines mono masters into colour with an optional Luminance layer, including real ORB + RANSAC channel alignment (Auto-Align Channels, on by default) |
| **Color Masks** | Port of Bill Blanshan's ColorMasksV4, extended from 6 to 12 colours |
| **Color Saturation** | Selective saturation adjustment |
| **SCNR** | Subtractive chromatic noise reduction (green removal) |

⭐ = added or substantially expanded in this release

---

## Mono support

Every tool in the app supports single-channel mono images, with the deliberate exception of tools that work on colour relationships *between* channels — Narrowband Normalization, Color Masks, Background Neutralization, Color Saturation, SCNR and SPCC.

---

## Requirements

- Windows
- No separate Siril installation needed — a portable Siril CLI is bundled
- Optional external engines, if you use those tools:
  - **GraXpert** for the GraXpert tool
  - **RC-Astro CLI** (BlurXTerminator / StarXTerminator / NoiseXTerminator) for the Xterminator Tools
  - **StarXTerminator or StarNet** to produce starless images for the Dust Lane Enhancer

Built with Python and CustomTkinter, packaged with PyInstaller.

### Running from source

The whole application is a single script:

```
AstroSuite_Pro_v1_0_4.py
```

```bash
python "AstroSuite_Pro_v1_0_4.py"
```

The bundled `Siril/bin/siril-cli.exe` must sit alongside it.

---

## Credits

AstroSuite Pro's native tools are ports of, or built from, real published work. Full credit to their authors:

- **Siril** — stacking and calibration engine
- **Bill Blanshan & Mike Cranfield** — Narrowband Normalization, Star Reduction, Screen Stars, Color Masks
- **David Payne & Mike Cranfield** — Generalised Hyperbolic Stretch (GPL v3)
- **Franklin Marek (Seti Astro)** — Blemish Blaster, Star Stretch, NB to RGB Stars
- **Riccardo Paterniti** — VeraLux HyperMetric Stretch
- **Carlos Sonnenstein & Oriol Lehmkuhl (PTeam)** — DarkStructureEnhance (GPL v3)
- **Alejandro Frangi et al. (1998)** — vesselness filter underlying the Dust Lane Enhancer; reference implementation from scikit-image
- **PixInsight** — RangeSelection and LinearFit algorithms, from published documentation
- **RC-Astro (Russell Croman)** — BlurXTerminator, StarXTerminator, NoiseXTerminator
- **GraXpert** team
