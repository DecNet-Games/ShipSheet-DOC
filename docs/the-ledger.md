---
layout: default
title: The Ledger
nav_order: 5
description: "The ShipSheet ledger workflow: one JSON record per content asset, keyed by GUID — how records are created, edited, and what happens on moves, renames and deletes."
---

# The Ledger
{: .no_toc }

## One record per content asset, kept in your project
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## What the ledger is

The ledger is a single JSON file — `Assets/ShipSheet/Ledger/ship-sheet-ledger.json`, storage format `schemaVersion: 1` — holding one **record** for every content asset ShipSheet tracks: art, models, textures, audio, fonts, video, animations, materials and text content. (Code is out of scope by design: UPM packages, DLLs and plugin licences are not ledger content — see [What v1 Is Not](./what-v1-is-not).)

Each record answers five questions about one asset:

- **What is it?** — display name and path.
- **Where did it come from?** — an origin class (`AssetStorePack`, `CcOrStockSite`, `AiGenerator`, `InHouse`, `Commissioned`, or `Unknown`) and the source's name: the pack, website, generator tool or studio.
- **Under what licence?** — the licence name as recorded, whether it prohibits commercial release, and a link or reference to the evidence (purchase proof, licence file, receipt).
- **Did AI make it, and how?** — AI involvement per Valve's 17 January 2026 taxonomy: `None`, `PreGenerated`, or `LiveGenerated`.
- **What credit does it require?** — whether attribution is required, and the exact verbatim credit line.

The field-by-field reference is [Ledger Fields](./ledger-fields).

## Records are keyed by GUID

A record is keyed by the asset's Unity **AssetDatabase GUID**, not its path. That one decision drives the ledger's behaviour:

- **Move or rename an asset** — the GUID survives, ShipSheet refreshes the cached path, and every provenance field stays as it was.
- **Delete an asset** — the record is **never silently deleted**. It is marked *orphaned* and appears in the [Review Queue](./backfill-and-review-queue), where you choose to remove the record or keep it and re-point it at a replacement asset. A shipped-then-deleted asset is exactly what a disclosure audit asks about, so the history stays yours to resolve.

## Record statuses

| Status | Meaning |
| :--- | :--- |
| `Recorded` | Provenance confirmed: origin, licence and the fields the licence requires are filled in. |
| `NeedsReview` | A record exists (from backfill or the import hook) but its provenance is not confirmed yet. |
| `Unrecorded` | The asset is known to the scan scope but has no confirmed record — this is what rule [RF-1](./red-flag-rules) reports. |
| `Orphaned` | The asset file was deleted; the record is kept as history until you resolve it in the Review Queue. |

## Working in the Ledger section

The **Ledger** section lists every record with its status. From here you can:

- **Edit a record** — set origin, source, licence, AI involvement and the attribution fields directly.
- **Run Backfill This Project** — create *Needs Review* entries for everything in scope that lacks one (see [Backfill & Review Queue](./backfill-and-review-queue)).
- **Jump from a flag** — a red flag's **Open Record** action lands on the exact record the [scan](./red-flag-scan) flagged.

## The ledger is yours

The file is plain JSON inside your project, designed to be committed to version control with the rest of the project — your version control is the sync; there is no team server and no cloud copy. Nothing is stored in the Library folder, and nothing leaves your machine: no account, no cloud, no telemetry. [Exports & Files](./exports-and-files) covers the CSV/JSON exports and where every ShipSheet file lives.
