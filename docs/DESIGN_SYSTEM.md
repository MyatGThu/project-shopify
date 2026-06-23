# Design System

The visual language is **relatable-glam**, derived from Melina's character
bible: *"gorgeous but attainable… model-off-duty… NOT cold luxury editorial."*
Polished, but warm and approachable — not icy/luxe. The default direction below
is implemented in the theme today.

---

## 1. Direction — relatable-glam

| Principle (from the bible) | How it shows up on the site |
| --- | --- |
| Relatable-glam, not cold luxury | Friendlier serif, lowercase casual voice, lifestyle imagery |
| Openly AI is "the edge" | A confident "meet melina" moment + honest disclosure |
| Products are real | Copy centres real, made-to-order goods; only the model is AI |
| Melbourne is a character fact | Laneways, cafés, terraces, the bay as imagery settings |

---

## 2. Typography

- **Heading:** **Lora** — a warm, contemporary humanist serif (friendlier than a
  cold Didone like Playfair). Set in the theme via the font picker.
- **Body:** **Inter** — clean, highly legible grotesque.
- **Upgrade path:** if your store's font library includes them, **Instrument
  Serif** or **Fraunces** read even more current — swap the heading font in the
  customizer (they're already in the CSS fallback stack).

**Casual voice in type:** eyebrows, nav, buttons, and the wordmark are
**lowercase** (her "lower-case for casual" rule). Headlines stay natural case;
the **last hero line is a grey-green italic** accent.

Change fonts in Online Store → Customize → Theme settings → Typography, or edit
`heading_font` / `body_font` in `config/settings_data.json`.

### Type scale
Fluid `clamp()` scale (~1.25 major third) in `assets/base.css`: `--fs-200`
(eyebrow) → `--fs-900` (hero display, up to ~7.5rem).

---

## 3. Color palette — "Bone & Bronze" retired, now from Melina's anchors

| Token | Hex | Drawn from |
| --- | --- | --- |
| `--color-bg` | `#F2F2F0` | cool-neutral paper (her cool-neutral skin rule) |
| `--color-surface` | `#FFFFFF` | cards, drawers |
| `--color-ink` | `#141414` | jet-black — her hair |
| `--color-muted` | `#6B6E6B` | cool grey |
| `--color-line` | `#E3E3DF` | cool hairline |
| `--color-accent` | `#6E7D71` | **grey-green — her signature eyes** |
| `--color-gold` | `#C2A35A` | **delicate gold — her jewellery (use sparingly)** |
| `--color-ink-bg` | `#141414` | dark sections |
| `--color-on-ink` | `#F2F2F0` | text on dark |

The grey-green is the brand's ownable accent (it's literally her eyes). Gold is a
*delicate* metallic detail only — hairlines, the marquee separator — never a fill.
Real warmth comes from Melina's imagery, not the UI.

---

## 4. Voice & copy

Direct, dry, self-aware, warm — **never try-hard**. First person where Melina
speaks; lowercase for casual chrome. Her canonical intro line — *"i make nice
things"* — is the hero headline.

**Openly-AI + real products (the reconciliation):**
> *"i'm melina — a model & content creator in melbourne. and i'm AI, not hiding
> it. the clothes, though, are real — made to order."*

This leans into the bible's openly-AI edge **and** keeps products real. An honest
"AI-generated model" line also satisfies platform/AU disclosure expectations.

---

## 5. Imagery direction

- **Natural, un-retouched** — visible texture, **keep the freckles**; no glossy
  over-grading.
- **Cool-skin-under-warm-light** — warm/golden light may fall on her, but her skin
  stays light and cool-neutral. Hold this in any colour grade.
- **Melbourne settings** — laneway cafés, terrace/warehouse interiors, trams, the
  bay, real golden hour. Authentic, photogenic, model-off-duty.
- **Aspect ratios** — favour **4:5** (portrait) and **9:16** (vertical), her native
  formats; plan for **vertical Reels-style video**. (Specs in `MELINA_ASSETS.md`.)

---

## 6. Motion principles

Quiet and intentional — never bouncy or gimmicky.

- **Reveals:** fade + rise as elements enter (`[data-reveal]`, theme.js); stagger
  groups with `[data-reveal-group]`.
- **Hero:** oversized type animates up line-by-line after the loader wipes.
- **Transitions:** her rule — *dissolves for lifestyle, cuts for fashion; never
  iris or smooth* (they read as AI). Our fades/cuts match.
- **Accessibility:** everything is gated behind `prefers-reduced-motion`; opted-out
  visitors get instant, transform-free content.

---

## Alternative directions (not default)

- **Editorial Luxe** — Playfair Display + Inter, bone & bronze, all-caps. More
  formal; the bible explicitly steers away from this "cold luxury" register.
- **Haute Minimal** — Cormorant Garamond + Montserrat. Boutique/airy.

---

## Sources

- Melina Character Bible (Rev 3.0, Melbourne) — internal
- [Typewolf — Best Google Fonts](https://www.typewolf.com/google-fonts)
- [GSAP — ScrollTrigger docs](https://gsap.com/docs/v3/Plugins/ScrollTrigger/)
