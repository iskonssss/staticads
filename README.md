# Forgecraft Ad Generator

A single-file, offline ad generator for **Forgecraft** (a 3D-printing workshop for kids in Singapore). It runs entirely in the browser using the Canvas API — upload a photo, type your copy, drag things into place, and export a ready-to-post ad as a PNG. There is no build step and no server: it's one static `index.html` with the brand fonts embedded, so it works offline and hosts as a static page.

**Live site:** https://iskonssss.github.io/staticads/

## How to use

1. **Upload an image** — click the upload box (or drag a photo onto it).
2. **Type your copy** into the fields: eyebrow (small caps), headline, subhead, and the bottom CTA bar.
3. **Drag to reposition** — pick a layer ("Move all text", Eyebrow, Headline, Sub, or Move photo), then drag it on the canvas. Use the placement buttons (Top L / Mid L / Btm L / Center) for quick anchors.
4. **Sliders** — adjust photo Vertical / Horizontal position, **Zoom**, and **Darkness** (scrim over the photo). Style options add a text panel, panel opacity, headline colour, and headline size.
5. **Format toggle** — switch between **1:1**, **4:5**, and **9:16** for different placements.
6. **Export PNG** — downloads at full resolution (1080px wide).
7. **Export / Load JSON** — saves all settings (including the embedded photo) so you can reload later and keep editing.

## Notes

- It's a **single static file** (`index.html`) with **no build step** and no dependencies.
- The fonts (Archivo, Plus Jakarta Sans, Space Grotesk) are **embedded as base64** inside the file, which is why it's large (~700 KB). This is intentional — it keeps the tool fully offline and ensures the canvas renders the correct brand fonts.
