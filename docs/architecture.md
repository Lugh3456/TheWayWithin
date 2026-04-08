# Architecture

## Project Overview

The Way Within is a **static single-page portal** hosted on GitHub Pages.

It uses a **hub-and-spoke model**:

- The hub (this project) is a landing page with cards for each mini site
- The spokes are separate GitHub repositories, each a standalone mini site
- The hub links out to the spokes — it does not embed or import their content

The site uses HTML + CSS only. No frameworks.

---

# Folder Structure

```
TheWayWithin/
  index.html          ← single portal page, all HTML and CSS in one file
  docs/
    readme.md         ← project overview
    ai-context.md     ← instructions for AI assistants
    architecture.md   ← this file
    plan.md           ← vision and objectives
    roadmap.md        ← phased delivery plan
```

There is no `src/`, `public/`, or `assets/` folder.
All CSS lives inside `<style>` tags in `index.html` for simplicity.

---

# Hub-and-Spoke Model

```
TheWayWithin (hub)
  ├── → Yijing (spoke)         github.com/lugh3456/Yijing
  ├── → ZengGuoFan (spoke)     github.com/lugh3456/ZengGuoFan
  ├── → DaoDeJing (spoke)      github.com/lugh3456/DaoDeJing
  └── → [future site] (spoke)
```

Each spoke is independently maintained. Adding a new spoke only requires
adding a new card to `index.html` — no other files need to change.

---

# Page Structure

The portal is a single HTML page with these sections in order:

```
<header>        ← site name + nav links
<section.hero>  ← tagline, heading, intro text
<main>
  .divider      ← "EXPLORE THE COLLECTION" label
  .cards-section
    article.site-card   ← one per mini site
    article.site-card.coming-soon  ← placeholder for next addition
<section.about-strip>  ← About this collection
<footer>
```

---

# CSS Architecture

All styles are in a `<style>` block inside `index.html`.

Styles are organised in sections:

```
TOKENS / VARIABLES     ← CSS custom properties (:root)
RESET & BASE           ← box-sizing, body, a
SKIP LINK              ← accessibility
HEADER / NAV           ← .site-header, .logo, nav
HERO                   ← .hero, .hero::before, .hero-tagline-zh
DIVIDER                ← .divider
SITE CARDS             ← .cards-section, .site-card, card children
COMING SOON CARD       ← .site-card.coming-soon, .coming-soon-badge
CATEGORY LABEL         ← .card-category
ABOUT STRIP            ← .about-strip
FOOTER                 ← footer
RESPONSIVE             ← @media breakpoints
```

---

# Card Grid

The cards use CSS Grid with `auto-fit`:

```css
grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
```

This means:
- 1 card → full width
- 2 cards → 2 columns
- 3 cards → 3 columns
- 4 cards → wraps to 2 rows of 2
- 5+ cards → continues to reflow automatically

No manual column count needs to be set when adding new cards.

---

# Responsive Breakpoints

| Breakpoint | Change |
|-----------|--------|
| > 600px | Default layout |
| ≤ 600px | Header stacks vertically, reduced padding |

The card grid reflows automatically — no explicit breakpoint needed for it.

---

# External Dependencies

Google Fonts (loaded via `<link>`):

- Noto Serif SC (headings, logo, Chinese card names)
- Noto Sans SC (body, nav, descriptions)

No other external dependencies.

---

# Hosting

GitHub Pages via the `lugh3456` account.

Deployment: push `index.html` to the repository root on the `main` branch.
GitHub Pages serves it automatically at:

https://lugh3456.github.io/TheWayWithin/
