---
layout: default
title: Red-Flag Rules
nav_order: 9
description: "RF-1 to RF-4 defined exactly as the scanner states them: unrecorded build content, non-commercial licence in a commercial project, font licence evidence, and missing attribution."
---

# Red-Flag Rules
{: .no_toc }

## The four rules, in the product's own words
{: .no_toc .text-delta }

The [scan](./red-flag-scan) evaluates exactly four rules. The descriptions and fix actions below are the scanner's own text — the same words the window shows and the reports export. An asset carries at most one flag, in the precedence order RF-1 → RF-3 (fonts) → RF-2 → RF-4.

---

## RF-1 — No provenance record

> **"Asset is included in the build but has no provenance record in the ledger."**
> Fix: *"Add a record in the Ledger or run Backfill to assign provenance."*

An asset inside the scan scope has no record at all, or its record is still `Unrecorded`. This is the most fundamental flag: with no record, the project cannot say where the asset came from, under what licence, or whether AI made it — and no other rule can be evaluated for it. It is also the easiest to prevent: the [import hook](./backfill-and-review-queue) queues every new import for a record, and **Backfill This Project** covers everything that predates ShipSheet.

## RF-2 — Non-commercial licence, commercial project

> **"Recorded licence is non-commercial, and this project is set to ship commercially."**
> Fix: *"Replace the asset with a commercially licensed alternative or obtain a commercial waiver."*

The record's `nonCommercial` flag is set, and the project's `shipsCommercially` [setting](./settings) is on. This is the planted problem in the [SampleHarbour](./sampleharbour) sample: the **Dockside Ambience Loop**, recorded as CC BY-NC 4.0 in a project set to ship commercially. The rule fires on *your record's* statement of the licence — ShipSheet does not read licence files or verify terms; if the record is wrong, correct the record.

## RF-3 — Font licence evidence unverifiable

> **"Font is sourced from a free font mirror site or lacks verifiable licence evidence."**
> Fix: *"Verify commercial redistribution rights and attach a valid licence evidence link."*

Fonts are singled out because their licences travel badly: a font file arrives, its licence PDF does not. A font (`.ttf`, `.otf`, `.ttc`, `.dfont`, `.fnt`) is flagged when any of these holds:

- its recorded **origin is `Unknown`**,
- its **evidence link is empty** — no purchase proof, licence file or receipt reference, or
- its **recorded source matches the bundled mirror-site list** (`Editor/RedFlags/Data/mirror-font-sites.txt` in the package) — known free-font mirror sites whose downloads carry no verifiable commercial terms.

For fonts, RF-3 takes precedence over RF-2: a mirror-sourced font is reported as the font risk even when it is also recorded non-commercial, because the evidence problem is the one to fix first.

## RF-4 — Attribution required, credit text missing

> **"Asset requires attribution according to its licence, but no credit text has been entered."**
> Fix: *"Enter the required attribution text in the Ledger record."*

The record says the licence **requires attribution** (`attributionRequired`), but the **credit line itself was never entered** (`attributionText` empty). Left alone, this is the quiet failure: the asset ships, the licence's one condition is a credit, and the [credits block](./credits-block) has nothing to print. Entering the exact line on the record clears the flag and feeds the credits generator in the same edit.

---

## What no rule does

No rule inspects an asset's contents, guesses at provenance, or judges a licence's legal effect. Every flag is a statement about **your records**: what they say, and what they fail to say. That boundary is deliberate — see [What v1 Is Not](./what-v1-is-not).
