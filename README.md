# Forgecraft Ad Generator

A single-file, offline ad generator for **Forgecraft** (a 3D-printing workshop for kids in Singapore). It runs entirely in the browser using the Canvas API — upload a photo, type your copy, drag things into place, and export a ready-to-post ad as a PNG. There is no build step and no server: it's one static `index.html` with the brand fonts embedded, so it works offline and hosts as a static page.

**Live site:** https://iskonssss.github.io/staticads/

This repo also contains the **[Forgecraft Leads CRM](https://iskonssss.github.io/staticads/crm.html)** (`crm.html`) — see [Leads CRM](#leads-crm) below.

## How to use

1. **Upload an image** — click the upload box (or drag a photo onto it).
2. **Type your copy** into the fields: eyebrow (small caps), headline, subhead, and the bottom CTA bar. (Optional: hit **✨ Generate ad copy** to have Claude draft all four — see "AI copy" below.)
3. **Drag to reposition** — pick a layer ("Move all text", Eyebrow, Headline, Sub, or Move photo), then drag it on the canvas. Use the placement buttons (Top L / Mid L / Btm L / Center) for quick anchors.
4. **Sliders** — adjust photo Vertical / Horizontal position, **Zoom**, and **Darkness** (scrim over the photo). Style options add a text panel, panel opacity, headline colour, and headline size.
5. **Format toggle** — switch between **1:1**, **4:5**, and **9:16** for different placements.
6. **Export PNG** — downloads at full resolution (1080px wide).
7. **Export / Load JSON** — saves all settings (including the embedded photo) so you can reload later and keep editing.

## AI copy (optional)

The **✨ Generate ad copy** button drafts the eyebrow / headline / subhead / CTA with Claude (Haiku 4.5). It's bring-your-own-key: paste your Anthropic API key once under **AI settings** — it's saved only in your browser's `localStorage`, never uploaded or committed, and is never written into exported JSON. The page calls the Claude API directly from the browser; only the text copy is generated, never your image. Roughly US$0.0015 per generation. The tool works fully without this — it's just a shortcut for first drafts you can then edit by hand.

## Leads CRM

`crm.html` is a phone-first CRM for working Meta Ads leads for the Beginner 3D Printing Session — same philosophy as the ad tool: one static file, no build step, no server, works offline.

**Live page:** https://iskonssss.github.io/staticads/crm.html

What it does:

- **🔥 Today queue** — the default view shows exactly who to work right now, in priority order: expired slot holds, holds running out, overdue follow-ups, new leads you've never called, then no-answer retries. No more guessing who you've contacted.
- **📌 Soft booking** — when a parent says yes on the phone but hasn't paid, soft-book a slot with a hold duration (24 h / 48 h / 3 days / custom deadline). The lead shows a live countdown, flips to **⏳ Running out** in the last 12 hours and **⌛ Expired** after the deadline — both jump to the top of the Today queue. One tap converts, extends the hold, or releases to nurture, and there are `{expiry}`-aware WhatsApp templates for hold confirmations and expiry chasers.
- **One-tap Call / WhatsApp** on every lead. After you tap Call and come back to the page, it prompts you to log the outcome.
- **Call logging** — picked up / no answer (attempt count), outcome (🎉 closed, 📅 follow up with a date, 🌱 nurture, ✖️ lost) and the objection (price, timing, kid too young…).
- **Import Meta Ads CSV** — download leads from Leads Centre or Ads Manager and import; both formats are auto-detected. Duplicates (by phone) are skipped, so you can safely re-import the full export every few days. Leads already marked **Converted** in Leads Centre come in as Won; extra form questions land in the lead's notes; rows with no phone number (e.g. Messenger/IG organic leads) are skipped and counted.
- **📣 Blast (nurture)** — pick a segment (nurture / lost / no answer…), write one message (use `{name}`), then tap Send per lead: WhatsApp opens pre-filled and personalised. Includes editable message templates.
- **Stats** — due now, to call, follow-ups, won, close rate.

**Where the data lives:** in the browser's `localStorage` on that device — nothing is uploaded anywhere. To use it on both phone and laptop, use **☰ → Export backup** on one device and **Restore / merge backup** on the other; merge keeps the most recently updated copy of each lead. The page nags you to back up if it's been more than a week.

## Notes

- It's a **single static file** (`index.html`) with **no build step** and no dependencies.
- The fonts (Archivo, Plus Jakarta Sans, Space Grotesk) are **embedded as base64** inside the file, which is why it's large (~700 KB). This is intentional — it keeps the tool fully offline and ensures the canvas renders the correct brand fonts.
