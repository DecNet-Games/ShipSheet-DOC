---
layout: default
title: Red-Flag Scan
nav_order: 8
description: "The ShipSheet red-flag scan: a deterministic, read-only audit of your own records over the content your build includes — scope, precedence, and the text and JSON reports."
---

# The Red-Flag Scan
{: .no_toc }

## A deterministic audit of your own records — read-only, every time
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## What the scan does

**Run Red-Flag Scan** (Red Flags section, or **Tools → Decnet Games → ShipSheet → Red-Flag Report**, which opens the window on the section and runs the scan) evaluates your [ledger records](./the-ledger) against the [four red-flag rules](./red-flag-rules) over a defined scope of assets. Every flag it raises carries three things:

- the **asset, named** (with its path),
- the **rule, in plain language** — what is wrong, in terms of your records,
- the **fix** — the one action that clears it.

The scan reports what your records say. It does not verify that a recorded licence is genuine, it does not look inside asset files, and it is not legal advice.

## The scan is read-only

The scanner is a pure evaluation over your records, the scope set, your [settings](./settings) and the bundled mirror-site list. **It never writes to the ledger or to any asset.** Running it a hundred times changes nothing in your project; acting on a flag is always your edit, in the Ledger, via the flag's **Open Record** action.

## Scan scope

Scope decides which assets the rules are evaluated over. It is a [setting](./settings), with two modes:

- **Build-included content (default)** — the dependencies of the enabled scenes in Build Settings, plus every in-scope asset under any `Resources` folder and under `StreamingAssets`. This is the content that actually ships — the scope the disclosure survey is about.
- **Whole project** — every in-scope content asset in the project, shipped or not. Useful for a periodic house-cleaning pass.

Only content assets can enter a scan — art, models, textures, audio, fonts, video, animations, materials and text content. Code and other out-of-scope assets are never flagged and never counted in the scan's "assets checked" total. Orphaned records are skipped by the scan: they wait in the [Review Queue](./backfill-and-review-queue) for your decision instead.

## One flag per asset, by precedence

An asset carries **at most one flag** — the most fundamental problem first:

1. **RF-1** — no record at all. Nothing else can be judged until the record exists.
2. **RF-3** — for fonts, unverifiable licence evidence is reported as the font risk, ahead of RF-2.
3. **RF-2** — a non-commercial licence in a commercial project.
4. **RF-4** — a required credit line that was never entered.

The full rule definitions are on the [Red-Flag Rules](./red-flag-rules) page. Flags are presented sorted by rule, then by asset name, and the same records in the same scope always produce the same report — the scan is deterministic.

## The reports

A scan produces two exports (written alongside the other generated files — see [Exports & Files](./exports-and-files)):

- **The text report** — the buyer-facing form: for each flag, the asset name and path, the rule in plain language, and the fix. A clean scan reports the scope and how many assets were checked. Rule IDs do not appear in the text report.
- **The JSON export** — the machine-readable form for your own pipeline: the scope used, and per flag the asset GUID, display name, **rule code** (RF-1 to RF-4), description and fix action.

![A scan result: the flag, named, with the fix written out]({{ "/assets/images/redflag-hit.png" | relative_url }})
