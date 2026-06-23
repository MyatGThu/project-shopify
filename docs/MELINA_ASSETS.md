# Imagery Guidelines (Melina)

How brand imagery of **Melina** is prepared and brought into the store so it
drops straight into the theme with no rework. Images are produced in batches with
your own image tooling, then imported into Shopify.

> Melina is the brand's (openly AI) model. The **products are real**, made-to-order
> items — keep all brand copy and imagery consistent with that.

---

## 1. Keep the look consistent

- Lock a small **reference set** (a few approved images) and reuse it for every
  batch, so Melina reads as the same person across shots.
- Keep her look constant; vary pose, garment, framing, and background per shot.
- Review each batch against the reference before importing; drop anything off-model.
- **Editorial direction:** warm, premium, generous negative space, soft natural or
  studio light. Keep backgrounds clean — Melina + the garment are the subject.
- **Natural texture:** keep freckles and real skin texture; avoid heavy retouch.
  Warm light may fall on her, but her skin stays light and cool-neutral.

---

## 2. Image specs (produce to these)

| Use | Aspect | Min resolution | Notes |
| --- | --- | --- | --- |
| Hero — desktop | 16:9 (or 21:9 cinematic) | 2400px wide | provide a mobile crop too |
| Hero — mobile | 4:5 portrait | 1400px wide | |
| Lookbook | 4:5 portrait | 1600px wide | full-figure, editorial |
| Product (on-model) | 4:5 portrait | 1600px wide | first product image |
| Cutout (PDP) | transparent PNG | subject ~2000px tall | clean silhouette |
| Section accent | flexible | 1200px+ | |

**Format:** deliver high-quality **JPG** (or PNG for transparency). Upload the
**originals** — Shopify's CDN auto-resizes and serves **WebP**, and the theme
already requests responsive `widths` per image.

**Garment fidelity:** the piece + print in the image should match the actual
product (colour, placement, fit) so customers get what's shown.

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

**A. Site / section imagery** (hero, lookbook, editorial accents)
1. Shopify admin → **Settings → Files** → upload the batch.
2. **Online Store → Customize** → set the image in the relevant section (Hero and
   Editorial split have image pickers).
3. Prefer **Files** for bulk imagery to keep the theme lightweight; reserve the
   repo's `assets/` for a few always-on static images.

**B. Product (on-model) images**
- Per product: admin → product → **Media** → upload; put the on-model shot **first**
  (it becomes `featured_media`, which the grids/PDP use).
- In bulk: Shopify **product CSV import** supports an `Image Src` column (a public
  image URL per row).

**C. Always add descriptive `alt` text** (accessibility + SEO).

---

## 5. Disclosure

- Melina is an **AI-generated model**; the **products are real**. Keep that
  distinction clear in copy.
- An honest "AI-generated model" note (footer / about) is good practice and meets
  platform expectations.
- Ensure imagery reflects what actually ships.

---

## Handoff checklist (per batch)

- [ ] Consistent with the reference set
- [ ] Correct aspect ratios + resolution for the intended use
- [ ] Named per the convention above
- [ ] Uploaded to Files (site imagery) and/or product Media (on-model)
- [ ] `alt` text written
