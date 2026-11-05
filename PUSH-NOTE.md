# PUSH-NOTE — ShipSheet-DOC (not yet pushed)

Status: **complete repo tree, built locally only.** Nothing has been created or pushed on GitHub.

## Target

- **Repo:** `ShipSheet-DOC` under the **DecNet-Games** org — `https://github.com/DecNet-Games/ShipSheet-DOC` (create it EMPTY, no auto-README, then push this tree to `main`).
- **Live URL after Pages is enabled:** https://decnet-games.github.io/ShipSheet-DOC/
- **Pages setting:** deploy from branch `main`, root (`/`). No custom workflow needed — the classic builder works with this tree.

## Why this tree builds clean on Pages

- `_config.yml` uses **`remote_theme: just-the-docs/just-the-docs`** with the `jekyll-remote-theme` plugin, and `baseurl: "/ShipSheet-DOC"` matching the repo name.
- `Gemfile` contains **only** `gem "github-pages", group: :jekyll_plugins` — no `just-the-docs` theme gem. That pairing is the known fix for the two historical errors: *"The just-the-docs theme could not be found"* and *"The github-pages gem can't satisfy your Gemfile's dependencies"* (the AS1-DOC annotations carried into the PERCH master prompt; PERCH-DOC's own fix commit landed the same change).
- `README.md`, `PUSH-NOTE.md` and the Gemfile are in `_config.yml`'s `exclude:` list, so neither renders as a site page.

## Contents pushed (19 site pages + media)

- `index.md` (Home) · `docs/` — Getting Started, Installation, Quick Start, The Ledger, Ledger Fields, Backfill & Review Queue, Red-Flag Scan, Red-Flag Rules, Disclosure Draft, Credits Block, Exports & Files, Settings, SampleHarbour Sample, What v1 Is Not, FAQ, Troubleshooting, Changelog, Support.
- `assets/images/` — 10 real product captures (Editor frames from the verified capture session) + the scan-landing GIF; `assets/videos/demo.mp4` — the real 35-second demo. All media is the product's own; no stock, no fake links.

## Push route (when BOSS runs it)

Per house rule, laptop git pushes need the push done from the laptop terminal (or BOSS clicks the credential prompt). Suggested sequence on the laptop:

```powershell
cd <folder-holding-this-tree>
git init
git add .
git commit -m "ShipSheet documentation site — Just the Docs, 19 pages"
git branch -M main
git remote add origin https://github.com/DecNet-Games/ShipSheet-DOC.git
git push -u origin main
```

Then enable Pages on the repo (Settings → Pages → main / root) if it does not auto-enable.

## After the site is live

1. Verify https://decnet-games.github.io/ShipSheet-DOC/ loads and the nav shows all sections.
2. The ShipSheet house-format description (`../DESCRIPTION-HOUSE.md`) carries this docs URL in its DOCUMENTATION link line — the description is applied to the portal draft only once the site resolves.

## What remains / open items

- Repo creation + push + Pages enable: **BOSS's step** (not done by the docs agent).
- No product Asset Store URL exists yet (draft only), so the site links the Decnet Games publisher page (118262) instead of a product page — swap in the product URL on Home/Installation after the listing goes live.
- Known product note carried honestly in the docs: the package's shipped EditMode test suite is fixture-dependent and is therefore not described with any pass claims anywhere on this site (see the capture session's VERIFY.md fix-lane record).
