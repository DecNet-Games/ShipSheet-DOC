---
layout: default
title: Backfill & Review Queue
nav_order: 7
description: "How existing project content gets records: the silent import hook for new assets, folder-grouped backfill for what is already there, and the Review Queue where provenance is confirmed."
---

# Backfill & Review Queue
{: .no_toc }

## How assets that are already in your project get their records
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## The import hook: new assets, from now on

ShipSheet installs a silent background asset postprocessor. When a content asset is imported, the hook queues it for a record — no dialog, no interruption, no import blocked. The asset appears in the **Review Queue** as *Needs Review* until you confirm where it came from.

The same hook watches deletions: when a tracked asset is deleted, its record is marked **orphaned** and surfaces in the Review Queue for your decision (remove the record, or keep it and re-point it at a replacement). Records are never silently deleted — see [The Ledger](./the-ledger).

## Backfill: everything that was already there

Click **Backfill This Project** in the **Ledger** section. Backfill walks the project and creates a *Needs Review* entry for every in-scope content asset that does not have a record yet:

- **Nothing is guessed.** Origin and licence start empty. The folder name is copied into the record's Notes as a hint only — a hint is not provenance, and the record does not become `Recorded` until you confirm it.
- **Content only.** Backfill covers the same content types as the ledger — art, models, textures, audio, fonts, video, animations, materials, text content. Code assets are never ledger content and never appear.

## The Review Queue: confirm by folder, not by file

![The Review Queue: unconfirmed records grouped by folder]({{ "/assets/images/review-queue.png" | relative_url }})

The **Review Queue** section collects everything awaiting a provenance decision — backfill entries, fresh imports, and orphaned records — **grouped by folder**. A content pack is usually one decision: confirm the group once (origin, tool or source, and licence set once per group) instead of repeating it per file. Records that do not fit the group can still be edited one by one in the [Ledger](./the-ledger).

## Why the queue matters

An asset sitting in the Review Queue is an asset whose story the project cannot yet tell. If it is inside your build scope with no confirmed record, the [red-flag scan](./red-flag-scan) reports it under [RF-1](./red-flag-rules) — by name, before submission week does. Keeping the queue at zero as you work is the whole habit ShipSheet is built around: two minutes when the asset arrives, instead of a reconstruction at ship time.
