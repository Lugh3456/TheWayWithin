# The Way Within — Master Portal

**The Way Within (修身之道)** is a master portal website that brings together a growing collection of classical Chinese wisdom sites under one hub.

Each mini site covers a distinct classical text or teacher. The portal acts as a gateway — presenting each site as a card and linking out to it. All mini sites share a unified visual identity with the portal.

---

# Portal Goals

- Provide a single entry point for all classical Chinese wisdom mini sites
- Present each mini site clearly with a name, description, and category
- Maintain a unified visual identity across all linked sites
- Signal that the collection is growing and open-ended

---

# Technology

HTML
CSS

No frameworks. No JavaScript dependencies. No build tools.
Hosted on GitHub Pages.

---

# Hosting

GitHub Pages via the `lugh3456` account.

Live URL: https://lugh3456.github.io/TheWayWithin/

---

# Folder Structure

```
TheWayWithin/
  index.html            ← the only page (all CSS inline in <style> block)
  docs/
    readme.md           ← this file
    architecture.md     ← technical structure
    plan.md             ← vision and objectives
    roadmap.md          ← phased delivery plan
    ai-context.md       ← instructions for AI assistants
```

Mini sites are separate GitHub repositories and are linked to, not included.

---

# Current Mini Sites

| Site | Chinese Name | GitHub Pages URL |
|------|-------------|-----------------|
| Yijing | 易經 | https://lugh3456.github.io/Yijing/ |
| Zeng Guofan | 曾國藩 | https://lugh3456.github.io/ZengGuoFan/ |
| Dao De Jing | 道德經 | https://lugh3456.github.io/DaoDeJing/ |

---

# Standardised Mini Site Structure

All mini sites follow the same folder structure:

```
MiniSite/
  index.html            ← home page (at root for GitHub Pages)
  [content-pages].html  ← all HTML at root
  css/
    style.css           ← all styles
  images/               ← assets
  docs/                 ← project documentation
  Backup/               ← dated backups (YYYY-MM-DD/)
```

---

# Design Philosophy

The portal feels calm, scholarly, spacious, and welcoming. It uses a warm parchment background, a deep ink header, and gold accents — a visual identity that is distinct from any individual mini site while feeling like a natural parent to all of them.

---

# Adding a New Mini Site

To add a new card, copy the article block in index.html, fill in the details, and remove the `coming-soon` class if present. The grid reflows automatically.

See `ai-context.md` for the exact card template.

---

# License

Personal educational project.
