# Portfolio Design Specification & Developer Handoff

This document outlines the detailed design system and implementation specifications for the portfolio website. The project combines the high-impact layout structure and dynamic energy of **The Governors Ball** website with the elegant, serif-focused aesthetic of **Flower Knows**.

---

## 1. Design Overview & Vision

- **Vibe / Aesthetic:** High-impact editorial elegance. Combines bold serif typography and soft pastel tones with aggressive modular layouts and dynamic motion.
- **Key References:**
  - *Governors Ball:* Grid layout, mobile responsiveness, full-width hero header, crisp hover micro-interactions, bold uppercase header hierarchy.
  - *Flower Knows:* Elegant serif typography, soft romantic palette, subtle decorative accents.

---

## 2. Typography

- **Heading Font:** `Manofa Bold`
- **Body Font:** `Manofa Light`
- **Scale & Treatment:**
  - **Headings:** Massive, uppercase, bold serif. Headings should feel commanding and expressive.
  - **Hero Header:** Displays the user's name prominently at the top of the full-width hero section.
  - **Body / Subtext:** Set in `Manofa Light` with relaxed line-height for readability against soft blue backgrounds.

---

## 3. Color Palette & Usage

| Element | Color Code | Visual Description | Usage / Application |
| :--- | :--- | :--- | :--- |
| **Background** | `#80AEE8` | Soft Sky Blue | Main page background, primary canvas |
| **Text** | `#5B0015` | Deep Burgundy / Wine | All primary headings, body text, contrast elements |
| **Accent** | `#80AEEB` | Vibrant Ice Blue | Links, button fills, card borders, tag badges, outline accents |

### Accent Usage Rules
The accent color (`#80AEEB`) is utilized for:
1. Primary button fills & interactive link containers.
2. Section dividers and structural card borders.
3. Category badges / project tags (e.g., `[01]`, `[PROJECT TYPE]`).
4. Subtle text-stroke outlines on decorative background text elements in the hero section.

---

## 4. Layout Architecture & Grid System

### Hero Section
- **Width:** `100vw` (Full-width / Edge-to-edge).
- **Placement:** The site owner's name sits prominently at the very top of the hero container.
- **Background Layer:** Fast-drifting flower animation rendering full-screen behind the hero text content.

### Grid Layout
- **Desktop (Laptop & Monitor):** Modular **3-to-4 block grid** layout for featured works, case studies, and info modules.
- **Mobile View (Phone Width):** Collapses strictly into a **single 1-column vertical feed** for seamless vertical scrolling.

```
DESKTOP (3 to 4 Columns)                 MOBILE (1 Column Vertical Feed)
+-----------------------------------+     +-----------------------------------+
|  [ NAME ]                         |     |  [ NAME ]                         |
|  FULL-WIDTH HERO CONTAINER        |     |  HERO CONTAINER                   |
+-----------------------------------+     +-----------------------------------+
| [ ITEM 1 ] [ ITEM 2 ] [ ITEM 3 ]  |     | [ ITEM 1 ]                        |
+-----------------------------------+     | [ ITEM 2 ]                        |
                                          | [ ITEM 3 ]                        |
                                          +-----------------------------------+
```

---

## 5. Interactive Components & Micro-Interactions

### Work List Buttons & Links
- **Default State:**
  - Shape: Rounded pill corners (`border-radius: 9999px`).
  - Fill: `#80AEEB` (Accent Ice Blue).
  - Text: `#5B0015` (Deep Burgundy).
  - Border: 1px solid `#5B0015`.
- **Hover State:**
  - **Color Swap:** Background flips to `#5B0015` (Burgundy) and text flips to `#80AEEB` (Ice Blue).
  - Transition: Snappy micro-interaction (`150ms cubic-bezier(0.4, 0, 0.2, 1)`).
  - Optional Transform: Slight scale lift (`transform: translateY(-2px)`).

---

## 6. Motion & Background Animation

- **Concept:** Fast-drifting flower particles across the viewport canvas.
- **Speed:** Fast velocity drifting diagonally or downward across the hero container.
- **Implementation Guidelines:**
  - Built using HTML5 Canvas or CSS keyframe SVG particles.
  - Flowers should feature slight opacity variations (`opacity: 0.4` to `0.8`) to keep foreground text legible (`#5B0015`).
  - Must support `prefers-reduced-motion` media queries to pause or slow down animation if requested by user accessibility settings.