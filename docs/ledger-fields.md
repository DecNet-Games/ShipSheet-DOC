---
layout: default
title: Ledger Fields
nav_order: 6
description: "Every field on a ShipSheet ledger record: origin class, source, AI involvement per Valve's 17 January 2026 taxonomy, licence, attribution, evidence, and status."
---

# Ledger Fields Reference
{: .no_toc }

## Every field on a record, as shipped in the package's own reference
{: .no_toc .text-delta }

---

Every content asset tracked by ShipSheet contains a record with the following provenance fields:

| Field Name | Type | Description |
|---|---|---|
| `assetGuid` | string | Persistent Unity AssetDatabase GUID identifying the asset. Survives file renames and moves. |
| `assetPath` | string | Cached relative path to the asset (e.g. `Assets/Textures/Hero.png`). |
| `displayName` | string | User-friendly display name, defaults to the asset filename. |
| `originClass` | OriginClass | Provenance source category: `AssetStorePack`, `CcOrStockSite`, `AiGenerator`, `InHouse`, `Commissioned`, or `Unknown`. |
| `sourceName` | string | Name of pack, website, generator tool, or studio. Mandatory for AI generator records. |
| `aiInvolvement` | AiInvolvement | Degree of generative AI per Valve 17 January 2026 taxonomy: `None`, `PreGenerated`, or `LiveGenerated`. |
| `licence` | string | Licence name as recorded (e.g. `Asset Store EULA`, `CC BY 4.0`, `OFL 1.1`). Mandatory for `Recorded` status. |
| `nonCommercial` | bool | Flag indicating if licence prohibits commercial release. Audited against `shipsCommercially` in settings. |
| `attributionRequired` | bool | Flag indicating whether the recorded licence requires a credit line. |
| `attributionText` | string | Exact verbatim text to place in in-game credits block. |
| `evidenceLink` | string | Link or reference to purchase proof, licence file, or receipt. |
| `notes` | string | Free-form notes. Backfill tool places source folder hint here. |
| `status` | RecordStatus | Workflow state: `Recorded`, `NeedsReview`, `Unrecorded`, or `Orphaned`. |
| `isOrphaned` | bool | True if the physical asset was deleted while keeping its historical record. |
| `recordedAt` | string | ISO-8601 UTC timestamp of creation. |
| `updatedAt` | string | ISO-8601 UTC timestamp of last modification. |

## How the fields drive the rest of ShipSheet

- **The [red-flag scan](./red-flag-scan)** reads four of these fields: a missing or `Unrecorded` record ([RF-1](./red-flag-rules)), `nonCommercial` against the project's `shipsCommercially` setting ([RF-2](./red-flag-rules)), a font's `originClass` / `evidenceLink` / `sourceName` ([RF-3](./red-flag-rules)), and `attributionRequired` with an empty `attributionText` ([RF-4](./red-flag-rules)).
- **The [disclosure draft](./disclosure-draft)** is built from records by `aiInvolvement`: each `PreGenerated` and `LiveGenerated` record contributes one line — its name, the tool in `sourceName`, and where it appears, taken from `notes`. A record with `aiInvolvement` unset contributes nothing; unrecorded content does not appear at all.
- **The [credits block](./credits-block)** is generated from `attributionText`, verbatim, for every record with `attributionRequired` set — grouped by `originClass`.
