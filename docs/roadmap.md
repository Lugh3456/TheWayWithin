# Roadmap — The Way Within

---

# Phase 1 — Foundation (Completed)

- Portal concept and design
- Documentation structure
- HTML + CSS portal page
- Card grid layout with auto-fit CSS Grid
- Design tokens (colour palette, typography)
- Three initial mini site cards (Yijing, ZengGuoFan, DaoDeJing)
- Coming Soon placeholder card

---

# Phase 2 — Unified Design System (Completed)

Applied shared design tokens across all three mini sites so visitors moving between the portal and a mini site feel continuity.

- Shared CSS custom properties (colours, fonts) adopted by all mini sites
- Portal bar ("← The Way Within · 修身之道") added to every page of every mini site
- Noto Serif SC + Noto Sans SC applied consistently across all sites
- Chinese subtitles added to all site headers (道德經, 易經, 曾國藩)
- Skip links and id="main-content" for keyboard accessibility on all pages
- Prev/Next navigation: chapter nav (DaoDeJing), hexagram nav (Yijing), practice nav (ZengGuoFan)
- Footer with portal link on all pages across all three mini sites
- Meta descriptions added to all home pages
- Standardised folder structure across all mini sites (css/, docs/, images/)
- ZengGuoFan restructured: pages moved from src/pages/ to root; public/css/ to css/
- Portal card URL for ZengGuoFan updated to https://lugh3456.github.io/ZengGuoFan/
- Documentation created for DaoDeJing and Yijing; updated for ZengGuoFan and TheWayWithin

---

# Phase 3 — Content Expansion

Add new mini sites to the portal as they are built or improved.

Possible additions:

- 論語 Analects of Confucius
- 孫子兵法 The Art of War
- 菜根譚 Caigen Tan (Vegetable Roots Discourse)
- Other classical texts or teachers

For each new addition:
- Build or update the mini site following the standardised folder structure
- Add a card to index.html
- Update this roadmap

---

# Phase 4 — Polish and Launch

- SEO optimisation for the portal page
- Performance review (font loading, layout shift)
- Full accessibility audit
- Deploy all sites to GitHub Pages
  - ✅ TheWayWithin portal — https://lugh3456.github.io/TheWayWithin/
  - ✅ Yijing — https://lugh3456.github.io/Yijing/
  - ✅ DaoDeJing — https://lugh3456.github.io/DaoDeJing/
  - ✅ ZengGuoFan — https://lugh3456.github.io/ZengGuoFan/ (deployed 2026-04-08)

---

# Phase 5 — PWA Support (Completed 2026-04-18)

- ✅ Generated gold ☯ icons (192×192 and 512×512) for the portal
- ✅ Added `manifest.json` with correct name, description, and colour scheme
- ✅ Added `sw.js` service worker (cache-first, offline fallback)
- ✅ Updated `index.html` with PWA meta tags and service worker registration

---

# Future Considerations

- Filter or search bar if the collection grows beyond 8–10 sites
- A brief "how to use this collection" guide for new visitors
- Possible custom domain name
