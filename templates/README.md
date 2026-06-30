# Ad templates

Loadable starting points for the [Forgecraft Ad Generator](../index.html). Each `.json` captures a layout (format, panel style, copy, colours, text position) — **the photo is intentionally left out** so you drop in your own image per ad.

## Easiest: the in-app picker

These presets are also built into the generator. In the controls, use **Start from a template** (just under Format) and pick one — it applies instantly and keeps your uploaded photo. No download needed; ideal on a phone. The `.json` files below are the same presets for downloading/sharing.

## How to use (download path)

1. Download the `.json` you want (on the GitHub file page, use **Download raw file**).
2. Open the ad generator, click **Upload an image** and add your photo.
3. Click **Load JSON** and pick the template — it sets the copy, panel, format, and text placement onto your photo.
4. Drag the photo / text and tweak the sliders to taste, then **Download PNG**.

(You can also load the template first and upload the photo after — either order works.)

## What's here

| File | Format | Style |
|------|--------|-------|
| `01-screen-time-1x1` | 1:1 | Split panel — green text column, photo on the right |
| `02-screen-time-9x16` | 9:16 | Photo top, green bottom band |
| `03-2.5-hours-1x1` | 1:1 | Photo with bottom gradient band, text low |
| `04-2.5-hours-9x16` | 9:16 | Full photo with scrim, text at the top |
| `05-holiday-well-spent-1x1` | 1:1 | Photo top, green bottom band |

## Notes

- `blockY` (vertical text position) and `hSize` (headline size) are starting points — adjust per photo.
- The floating gold **price pill** is now a real draggable layer: tick **Price pill** in the Copy section, edit the text, then choose **Move pill** under Text placement and drag it on the canvas. Template 01 has it switched on.
