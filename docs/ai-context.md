# AI Development Context — The Way Within

Always read this file before modifying the site.

---

# Current State
Last updated: 2026-04-18
Phase: Phase 3 — Content Expansion
Last completed: Phase 5 complete — PWA support added (manifest.json, sw.js, icons/, PWA meta tags in index.html)
In progress: —
Next up: —

---

# Project Purpose

The Way Within (修身之道) is a **master portal** — a hub page that links out to a growing collection of classical Chinese wisdom mini sites.

It is not a content site. It does not host articles or lessons.
Its job is to present each mini site as a card and link to it.

---

# PWA Files

Added 2026-04-18. The portal is now installable as a PWA.

| File | Purpose |
|------|---------|
| `manifest.json` | PWA manifest — name, colours, icon paths |
| `sw.js` | Service worker — cache name `the-way-within-v1`, cache-first strategy, offline fallback to index.html |
| `icons/icon-192.png` | Gold ☯ on dark background, 192×192 |
| `icons/icon-512.png` | Gold ☯ on dark background, 512×512 |

When bumping the service worker cache (e.g. after a significant update), increment the version in `sw.js`: `the-way-within-v2`, etc.

---

# Technology Constraints

The project uses:

HTML
CSS

Do NOT introduce:

React, Next.js, Vue, Tailwind
Build tools or Node dependencies
JavaScript (unless trivial and clearly justified)

The site must remain static and deployable directly to GitHub Pages.

---

# Design Tokens

All colours are defined as CSS custom properties in `:root` inside `index.html`.

| Token | Value | Usage |
|-------|-------|-------|
| `--bg` | `#f5f0e8` | Page background (warm parchment) |
| `--surface` | `#ffffff` | Card background |
| `--ink` | `#1c1a14` | Header and footer background |
| `--ink-light` | `#3a3528` | Hero background |
| `--gold` | `#a07830` | Accent, borders, buttons |
| `--gold-light` | `#c9a75a` | Logo, hero tagline, section headings |
| `--text` | `#2d2a22` | Body text |
| `--muted` | `#6b6455` | Secondary text, card descriptions |
| `--border` | `#ddd5c0` | Card borders |
| `--radius` | `8px` | Card border radius |

Do not introduce new hardcoded colour values. Use the tokens above.

---

# Typography

Noto Serif SC — headings, logo, card Chinese names
Noto Sans SC — body text, navigation, card descriptions

Both loaded from Google Fonts. Do not switch fonts.

---

# Key CSS Classes

| Class | Purpose |
|-------|---------|
| `.site-header` | Top navigation bar |
| `.hero` | Dark hero banner with tagline and heading |
| `.cards-section` | CSS Grid container for all site cards |
| `.site-card` | Individual mini site card |
| `.site-card.coming-soon` | Placeholder card for a future mini site |
| `.card-category` | Small label above the card title |
| `.card-zh` | Chinese name in Noto Serif SC |
| `.card-en` | English name in gold |
| `.card-desc` | Description text |
| `.card-tags` | Row of topic tags |
| `.tag` | Individual tag pill |
| `.card-link` | "Explore →" button |
| `.about-strip` | Dark band with the About section |
| `.divider` | Section label with gold underline |

Do not rename these classes unless necessary.

---

# Current Mini Site URLs

| Site | URL |
|------|-----|
| Yijing | https://lugh3456.github.io/Yijing/index.html |
| ZengGuoFan | https://lugh3456.github.io/ZengGuoFan/index.html |
| DaoDeJing | https://lugh3456.github.io/DaoDeJing/index.html |

All mini sites have index.html at their repository root.
Do not add /src/pages/ or any subfolder prefix to these URLs.

---

# Adding a New Mini Site Card

Copy this block and place it inside `.cards-section` before the `coming-soon` card.
Fill in all placeholder values. Remove the `coming-soon` card when no longer needed.

```html
<article class="site-card">
  <div class="card-symbol">SYMBOL</div>
  <p class="card-category">Category Label</p>
  <div class="card-titles">
    <span class="card-zh">中文名</span>
    <span class="card-en">English Name · Subtitle</span>
  </div>
  <p class="card-desc">
    One to three sentences describing the text or teacher and what the site covers.
  </p>
  <div class="card-tags">
    <span class="tag">Tag 1</span>
    <span class="tag">Tag 2</span>
  </div>
  <a href="URL_TO_MINI_SITE" class="card-link" target="_blank" rel="noopener">
    Explore [Name] →
  </a>
</article>
```

For the card symbol, use a Unicode character that suits the content —
e.g. ☰ (trigrams), ☯ (yin-yang), ✦ (star), 論 (Chinese character), etc.

---

# Standardised Mini Site Structure

All mini sites in the collection use this folder structure:

```
MiniSite/
  index.html            ← home page at root (required for GitHub Pages)
  [content-pages].html  ← all HTML at root
  css/style.css         ← all styles
  images/               ← assets
  docs/                 ← documentation (readme, architecture, plan, roadmap, ai-context)
  Backup/               ← dated backups (YYYY-MM-DD/)
```

When building or restructuring a mini site, always follow this pattern.

---

# What Not to Change

- The CSS custom properties in `:root`
- Font imports — both Noto Serif SC and Noto Sans SC must remain
- The hero `::before` watermark character — decorative only
- The skip link — required for accessibility
- The `target="_blank" rel="noopener"` on card links — required for external links
- Mini site URLs — all index.html files are at repository root

---

# Development Philosophy

Prefer simple HTML and clean structure.
Always create a dated Backup/ folder before modifying files.
Verify locally before pushing to GitHub.
