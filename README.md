# 283adams.org — Adams Street Foundation site

Static site for the Adams Street Foundation, served by GitHub Pages.

## Structure
- `index.html` — homepage (rebuilt + upgraded from the Squarespace original, Aug 2026)
- `2026benefit/` — PERMANENT REDIRECT to the canonical benefit page at https://www.sljhs.org/2026benefit (decision 8/30). The URL is printed on the benefit invitations — never rename or delete the redirect. The retired page's copy (mission text, 100% stat, college list, support bullets) is archived at `ops/benefit-2026/benefit-page-archive-2026-08.html` in Helper.
- `parents/` — Parent Guide to the College Process (source: Helper `outreach/parent-guide-class-of-2027.html`)
- `fly-ins/` — Fly-in programs directory (GENERATED: edit `reference/fly-in-programs.csv` in Helper, run `scripts/build_flyins.py`, copy the output here)
- `colleges/` — College Research Guide (GENERATED: profiles live in Helper `reference/colleges/`, joined to the fly-in CSV and need-met CSV by `scripts/build_colleges.py` → `outreach/college-guide.html`; copied here by `publish_site.py`)
- `common-app/` — Common App Camp deck page + PDF (source pptx in Helper `curriculum/common-app-camp-2026/`)
- `assets/` — images (downloaded from the old Squarespace CDN) + `site.css` (shared stylesheet for homepage/benefit/common-app; parents & fly-ins pages are self-contained)
- `CNAME` — custom-domain binding for GitHub Pages. Do not delete.

## Publishing
Push to `main`; GitHub Pages deploys automatically (Settings → Pages → Deploy from branch `main` / root).

**Refreshing `/parents`, `/fly-ins`, and `/colleges`: run `python3 scripts/publish_site.py` from the Helper root — never copy the outreach builds in by hand.** The script re-applies the site-only injections the outreach sources deliberately lack: the noindex meta (preview phase; flip `NOINDEX = False` in the script at launch) and the cross-nav bar back to the homepage and sibling resources. A bare copy silently drops both.

## Rules
- Everything in this repo is PUBLIC. No student names, no internal notes, no unpublished stats.
- Impact figures come from the published SLJ School Profile 2026 only.
- Before every push: re-run the publish-safety sweep (see Helper CLAUDE.md, "Public site" section).
