# TAP Athletes — Logo

A fresh logo system for TAP Athletes. The old diamond / "TAP" / home-plate mark
is gone. The new mark is a **baseball seam** — the row of stitches a pitcher
grips — arcing over the wordmark. It reads simply as **TAP Athletes**.

Open `preview.html` in a browser to see the whole set.

## Design notes

- **Concept:** the seam/stitches = pitching, grip, command. A dynamic swoosh for
  the icon; a symmetric arc over the wordmark for the primary lockup.
- **Type:** Barlow Condensed Bold — the condensed face used in the site hero.
  All text is converted to **vector outlines**, so the files render identically
  with no font installed.
- **Approach:** "radical simplicity — monochrome base + one bold accent,"
  informed by the [open-design](https://github.com/nexu-io/open-design) Nike
  design-system reference. Bold, no-nonsense, athletic.
- **Palette** — the **current site** colors (cream + ink + the green/rust
  accents), not the retired navy/blue:

  | Token | Hex | Use |
  |-------|-----|-----|
  | Ink    | `#1A1A1A` | wordmark, dark backgrounds |
  | Cream  | `#FAF9F7` | light backgrounds |
  | Rust   | `#C4501C` | seam accent (default — warm, baseball-red) |
  | Forest | `#1B3D2F` | seam accent (alternate — the "Get the App" green) |

  The seam carries the only color; the type stays ink/cream. Pick **rust** or
  **forest** as the brand accent — both lockups are provided.

## Files

### Vector (SVG)
| File | Description |
|------|-------------|
| `tap-logo-stacked.svg` | Primary lockup — seam arc over `TAP` / `ATHLETES`. Rust seam. |
| `tap-logo-stacked-forest.svg` | Same, forest-green seam. |
| `tap-logo-stacked-reverse.svg` | For dark backgrounds — cream type, rust seam. |
| `tap-logo-horizontal.svg` | Seam swoosh + `TAP` / `ATHLETES`, horizontal. Rust. |
| `tap-logo-horizontal-forest.svg` | Horizontal, forest seam. |
| `tap-logo-horizontal-reverse.svg` | Horizontal for dark backgrounds. |
| `tap-seam.svg` / `tap-seam-ink.svg` / `tap-seam-forest.svg` | The seam mark on its own (rust / ink / forest). |
| `tap-app-icon.svg` | Seam on an ink rounded-square tile. |

### Raster (PNG)
| File | Description |
|------|-------------|
| `icon-32 / 96 / 192 / 512.png` | App / favicon — ink tile + rust seam. |
| `apple-touch-180.png` | iOS home-screen icon. |
| `tap-og-1200x630.png` | Open Graph / social share — stacked lockup on cream. |

## Regenerating

SVGs are produced with `opentype.js` (outlining Barlow Condensed) plus a small
seam-stitch generator; PNGs are rasterized from the SVGs with a headless
browser. Wordmarks are generated at a large reference size and scaled down in
the transform — this avoids a `toPathData` rendering glitch that corrupts
condensed glyphs at small font sizes. If you change geometry, re-run that step
so outlines and rasters stay in sync.
