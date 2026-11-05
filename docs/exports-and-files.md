---
layout: default
title: Exports & Files
nav_order: 12
description: "Where every ShipSheet file lives: the ledger, settings and exports under Assets/ShipSheet, the CSV/JSON ledger exports, and the generated document files."
---

# Exports & Files
{: .no_toc }

## Everything ShipSheet writes, and where it writes it
{: .no_toc .text-delta }

---

## All project data lives under `Assets/ShipSheet/`

ShipSheet writes nothing outside your project, and everything it creates in your project sits in one folder:

| Path | What it is |
| :--- | :--- |
| `Assets/ShipSheet/Ledger/ship-sheet-ledger.json` | The ledger — one record per content asset, storage format `schemaVersion: 1`. Plain JSON, designed to be committed to version control. |
| `Assets/ShipSheet/Settings/ShipSheetSettings.asset` | The project [settings](./settings): ships-commercially, scan scope, project name, template selection. |
| `Assets/ShipSheet/Exports/` | Everything generated: disclosure drafts, credits blocks, scan reports, ledger exports. |

Deleting the package removes the tool; these files remain as ordinary project files — your record, yours to keep or delete (see [Installation](./installation)).

## Ledger exports (Setup & Health)

**Export Ledger (CSV)** and **Export Ledger (JSON)**, in the **Setup & Health** section, write the full ledger in open formats at any time — for the spreadsheet or pipeline you already run, and as the backup to take before any manual ledger operation (the shipped guidance for resetting a ledger starts with an export; see the [FAQ](./faq)).

![Setup & Health: setup, verification and the ledger exports]({{ "/assets/images/setup-health.png" | relative_url }})

## Generated documents

Each generator writes into `Assets/ShipSheet/Exports/`:

- **Disclosure draft** — a `.txt` (the Steamworks paste target) and a `.md` (your team record) in one action. Format: [Disclosure Draft](./disclosure-draft).
- **Credits block** — the attribution text file. Format: [Credits Block](./credits-block).
- **Red-flag report** — a plain-text report (asset, rule in plain language, fix; a clean scan states the scope and the assets checked) and a JSON export (scope plus per-flag GUID, name, rule code, description and fix action) for your own tooling. Format: [Red-Flag Scan](./red-flag-scan).

## What never leaves the machine

Exports are files in your project, full stop. ShipSheet makes no network calls, holds no account, and sends no telemetry — if a document needs to reach Steamworks, a teammate, or a lawyer, you carry it there, which is the point: the record stays under your control from creation to submission.
