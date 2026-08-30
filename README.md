# 283adams.org — Adams Street Foundation site

Static site for the Adams Street Foundation, served by GitHub Pages.

## Structure
- `index.html` — homepage (rebuilt + upgraded from the Squarespace original, Aug 2026)
- `2026benefit/` — 2026 Benefit page. URL preserved from the old site (likely printed on invitations). Do not rename.
- `parents/` — Parent Guide to the College Process (source: Helper `outreach/parent-guide-class-of-2027.html`)
- `fly-ins/` — Fly-in programs directory (GENERATED: edit `reference/fly-in-programs.csv` in Helper, run `scripts/build_flyins.py`, copy the output here)
- `common-app/` — Common App Camp deck page + PDF (source pptx in Helper `curriculum/common-app-camp-2026/`)
- `assets/` — images (downloaded from the old Squarespace CDN) + `site.css` (shared stylesheet for homepage/benefit/common-app; parents & fly-ins pages are self-contained)
- `CNAME` — custom-domain binding for GitHub Pages. Do not delete.

## Publishing
Push to `main`; GitHub Pages deploys automatically (Settings → Pages → Deploy from branch `main` / root).

**Refreshing `/parents` and `/fly-ins`: run `python3 scripts/publish_site.py` from the Helper root — never copy the outreach builds in by hand.** The script re-applies the site-only injections the outreach sources deliberately lack: the noindex meta (preview phase; flip `NOINDEX = False` in the script at launch) and the cross-nav bar back to the homepage and sibling resources. A bare copy silently drops both.

## Rules
- Everything in this repo is PUBLIC. No student names, no internal notes, no unpublished stats.
- Impact figures come from the published SLJ School Profile 2026 only.
- Before every push: re-run the publish-safety sweep (see Helper CLAUDE.md, "Public site" section).
