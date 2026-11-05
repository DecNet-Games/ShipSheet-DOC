---
layout: default
title: Getting Started
nav_order: 2
description: "The core ShipSheet concepts: the provenance ledger, the import hook and review queue, the red-flag scan, and the two generated documents."
---

# Getting Started with ShipSheet
{: .no_toc }

## The ideas behind every ShipSheet workflow
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## 1. One window, five sections

Everything happens in the ShipSheet Home window — **Tools → Decnet Games → ShipSheet → ShipSheet Home** in the Unity Editor menu. The menu's section items (Ledger, Red-Flag Report) open the same window on the section you asked for; there are no orphaned feature windows. The window has five sections:

- **Setup & Health** — one-click setup and verification, ledger export.
- **Ledger** — every record, editable.
- **Review Queue** — assets that still need a provenance decision, grouped by folder.
- **Disclosure & Credits** — the two generators and their previews.
- **Red Flags** — the scan and its report.

First launch shows a welcome block with **Open Samples** and **Run Setup / Verify Install**. After setup there is nothing else to configure before your first record.

![The ShipSheet welcome screen on first run]({{ "/assets/images/welcome.png" | relative_url }})

## 2. The ledger is the product

The ledger is a single JSON file in your project — `Assets/ShipSheet/Ledger/ship-sheet-ledger.json` — holding one **record** per content asset: its origin, source, licence, AI involvement, and the exact credit line its licence requires. Records are keyed by the asset's Unity **GUID**, so a record survives the asset being moved or renamed, and a deleted asset's record is kept as **orphaned** history instead of vanishing.

Everything else in ShipSheet — the scan, the disclosure, the credits — reads this one file. [The Ledger](./the-ledger) page covers the workflow; [Ledger Fields](./ledger-fields) is the field-by-field reference.

## 3. Records arrive two ways

- **The import hook.** A silent background postprocessor notices content assets as they are imported and queues them for a record. Imports are never interrupted; the asset simply appears in the [Review Queue](./backfill-and-review-queue) until you confirm its provenance.
- **Backfill.** For a project that already has content, **Backfill This Project** walks the project and creates a *Needs Review* entry for every in-scope content asset without a record — grouped by folder, so a pack is confirmed once, not file by file. Nothing is guessed: origin and licence start empty.

## 4. The scan reads records, not tea leaves

**Run Red-Flag Scan** evaluates your records against [four deterministic rules](./red-flag-rules) over a defined [scope](./red-flag-scan) — by default, the content your build actually includes. The scan is **read-only**: it never writes to the ledger or any asset. Every flag names the asset, states the rule in plain language, and writes out the one action that clears it. ShipSheet reports what your records say — it does not verify licences, and it is not legal advice.

![The Red Flags section: the planted problem, named, with its fix]({{ "/assets/images/redflag-hit.png" | relative_url }})

## 5. The documents are generated, not retyped

From the same records, the **Disclosure & Credits** section generates:

- The **Steam disclosure draft** — in the shape of Valve's current survey (the v1 template is based on Valve rules as of **17 January 2026**), with a pre-generated section naming your AI-assisted asset sets and a live-generated section naming your runtime AI features. Written as plain text (the Steamworks paste target) and Markdown (your team record).
- The **credits block** — the recorded credit lines, exactly as recorded, grouped by origin class.

You stay the submitter: ShipSheet holds no Steam credentials and submits nothing. [Disclosure Draft](./disclosure-draft) and [Credits Block](./credits-block) cover both generators, and [What v1 Is Not](./what-v1-is-not) states the boundaries in full.

---

## Where to go next

- New install? [Installation](./installation), then the [Quick Start](./quick-start).
- Recording an existing project? [Backfill & Review Queue](./backfill-and-review-queue).
- Want to see the whole product on known data first? [The SampleHarbour Sample](./sampleharbour).
