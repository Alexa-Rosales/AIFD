# Project Handoff: Parametric Poster Generator — Making Time 17

## 1. Project Overview
* **Project Name:** Parametric Poster Generator — Making Time 17
* **Design Aesthetic:** David Rudnick / *Making Time* graphic design style—featuring heavy modular display typography, classical serif lineup lists, geometric background container shapes, scientific grid crosshairs, and high-contrast chromatic palettes.
* **Core Technology Stack:** 
  * Single-file HTML5 application (`index.html`)
  * Embedded modular SVG canvas
  * Google Fonts (`Foldit`, `Cormorant Garamond`, `Space Mono`, `Syne Mono`)
  * Client-side vector-preserving PDF export via `jsPDF` & `svg2pdf.js`

---

## 2. Key Features & Implementation Architecture

### A. Dynamic Botanical Specimen Generator
* Contains **four distinct multi-layered vector specimens** (`#specimen-rose`, `#specimen-fern`, `#specimen-lotus`, `#specimen-blossom`), each built with radial glow gradients, scientific coordinate grids, and unique cyberpunk colorways.
* Randomization cycles through the specimen library while dynamically updating the corresponding archival name and classification numbers.

### B. Archival Proximity Labeling
* Scientific classification text metadata (Specimen number, botanical archive title, and coordinate grid data `X / Y / Z`) is positioned directly alongside the botanical illustration asset to emulate authentic archival museum charts.

### C. High-Contrast Typography & Layer Separation
* Decoupled the outer workspace background from the actual SVG poster background (`<rect id="svg-bg">`) to guarantee clean structural framing.
* Placed all typography and titles on the topmost layer (`<g id="layer-typography">`) with forced high-contrast text fills so elements never blend into or get hidden behind background blobs.

### D. Interactive Control Sidebar
* **Chromatic Palettes:** Quick presets (*Acid Neon*, *Monochrome*, *Sunset*) plus custom color pickers for background, blob tones, outlines, and main text.
* **Typography & Content Editor:** Real-time text inputs and textareas for the vertical title, subtitle, date block, line-up, venue details, and footer badges.
* **Geometry & Scaling:** Fine-tune slider for archive specimen scaling.
* **Randomize & Reset:** One-click full randomization of colors, specimen types, layout variations, and typography presets, alongside a reset defaults button.

### E. Vector-Preserving PDF Export
* Direct client-side export using `jsPDF` and `svg2pdf.js`, generating crisp, high-resolution vector PDFs at exact poster dimensions (`600x900 pt`) without rasterization loss.

---

## 3. File Structure & Deployment

* **`index.html`**: Self-contained application file incorporating HTML markup, embedded CSS styling, SVG template definitions, and vanilla JavaScript control logic. No build tools, package managers, or server environments are required.

### How to Run:
1. Save the application code into a file named `index.html`.
2. Open the file directly in any modern web browser (Chrome, Firefox, Safari, or Edge).