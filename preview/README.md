# Static preview (dev only)

`preview/index.html` is a **plain HTML** mockup of the homepage that uses the
real design system (`../assets/base.css`) and motion (`../assets/theme.js`,
`../assets/loading.js`). It lets you **see the look, loading screen, and GSAP
scroll animations in any browser without Shopify**.

It is **not** part of the Shopify theme (Shopify ignores this folder on upload),
and it has **no live products or checkout** — content is hardcoded. For the real
store, use `shopify theme dev` (see `../docs/SHOPIFY_SETUP.md`).

## How to open it

**Easiest:** clone/pull the branch, then double-click `preview/index.html` (it
opens via `file://`). GSAP loads from a CDN, so stay online the first time.

**Recommended (a tiny local server avoids any `file://` quirks):**

```bash
# from the repo root
python3 -m http.server 8000
# then open http://localhost:8000/preview/
```

## Notes

- The **loading screen shows once per browser session.** To see it again, open a
  new private/incognito window, or clear sessionStorage for the page.
- The hero uses a **gradient placeholder** (no Melina image yet) — that's the
  current real state. Drop a campaign image in later per `../docs/MELINA_ASSETS.md`.
- If you set OS-level **"reduce motion,"** animations are intentionally disabled
  and everything appears instantly (by design, for accessibility).
