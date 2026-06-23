# Melina — Brand Model Asset Workflow

**Melina** is the brand's AI model. Her imagery is **produced externally in
batches** (e.g. the ChatGPT image tools or your **Project-AI pipeline**), then
imported into Shopify and wired into the theme. This doc defines the **specs and
conventions** so a batch drops straight in with no rework.

> Generation happens in your pipeline. This repo only consumes the finished
> images — so the rules below are about *format, naming, and placement*.

---

## 1. Keep Melina on-model (consistency)

The #1 risk with batch generation is drift — Melina looking like a different
person between batches. Mitigate it:

- **Maintain a character sheet.** A short, fixed description (face, hair, skin,
  body, age, vibe) + 3–5 locked reference images. Feed the *same* reference into
  every batch; when the tool supports an image/seed input, reuse it.
- **Lock the look, vary the scene.** Keep Melina constant; change pose, garment,
  framing, and background per shot.
- **QA each batch** against the reference before importing; discard drifters.
- **Editorial direction:** warm, premium, generous negative space, soft
  daylight/studio. Melina + the garment are the subject — keep backgrounds clean.

---

## 2. Image specs (produce to these)

| Use | Aspect | Min resolution | Notes |
| --- | --- | --- | --- |
| Hero — desktop | 16:9 (or 21:9 cinematic) | 2400px wide | provide a mobile crop too |
| Hero — mobile | 4:5 portrait | 1400px wide | |
| Lookbook | 4:5 portrait | 1600px wide | full-figure, editorial |
| Product (on-model) | 4:5 portrait | 1600px wide | first product image |
| PDP cutout | transparent PNG | subject ~2000px tall | clean silhouette |
| Section accent | flexible | 1200px+ | |

**Format:** deliver high-quality **JPG** (or PNG for transparency). Upload the
**originals** — Shopify's CDN auto-resizes and serves **WebP**, so you don't
pre-optimize. The theme already requests responsive `widths` per image.

**Garment fidelity:** the piece + print in the image should match the actual POD
product (color, placement, fit) so customers get what's shown.

---

## 3. Naming convention

```
melina_{campaign}_{subject}_{aspect}_{nn}.{ext}
```

Examples:
- `melina_ss26_tee-noir_4x5_01.jpg`
- `melina_ss26_hero-rooftop_16x9_01.jpg`
- `melina_ss26_hoodie-bone_cutout_01.png`

Consistent names make bulk upload, sorting, and product matching painless.

---

## 4. Import a batch into the store

**A. Site/section imagery** (hero, lookbook, rich-text accents)
1. Shopify admin → **Settings → Files** → upload the batch.
2. In **Online Store → Customize**, set the image in the relevant section
   (the Hero section has an image picker; more picker-driven sections are coming
   in Phase 1).
3. For a few always-on static images you can instead drop them in this repo's
   `assets/` folder and reference them — but prefer **Files** for bulk imagery to
   keep the theme lightweight.

**B. Product (on-model) images**
- Per product: open the product in admin → **Media** → upload. Put the on-model
  shot **first** (it becomes `featured_media`, which the grids/PDP use).
- In bulk: Shopify **product CSV import** supports an `Image Src` column (a
  public image URL per row) — handy for large catalogs. POD apps can also push
  mockups automatically; we lead with Melina shots and use mockups as secondary.

**C. Always add `alt` text** (accessibility + SEO) describing Melina + garment.

---

## 5. Optional: Higgs Field for post-processing

Even though stills are made in your pipeline, the **Higgs Field MCP** (connected
in this session) is useful for *editing* finished images without re-generating:

- `remove_background` → clean transparent PDP cutouts
- `upscale_image` → 2K/4K for hero/retina
- `outpaint_image` → extend a shot into a full-bleed hero
- `reframe` → retarget aspect ratios (e.g. 4:5 → 16:9)
- `generate_video` → a short hero loop from a still

Say the word and I can run any of these on a batch you provide.

---

## 6. Disclosure & ethics

- Consider an honest, low-key disclosure that brand imagery is AI-generated where
  appropriate (some regions/platforms increasingly expect it).
- Ensure imagery reflects what actually ships, to avoid misleading customers.

---

## Handoff checklist (per batch)

- [ ] Passes Melina consistency QA against the character sheet
- [ ] Correct aspect ratios + resolution for intended use
- [ ] Named per the convention above
- [ ] Uploaded to Files (site imagery) and/or product Media (on-model)
- [ ] `alt` text written
