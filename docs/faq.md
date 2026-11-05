---
layout: default
title: FAQ
nav_order: 16
description: "ShipSheet questions answered: where the ledger lives, resetting it, renames and deletes, template updates, AI detection, and Steam submission."
---

# Frequently Asked Questions
{: .no_toc }

---

## Where is my ledger saved?

At `Assets/ShipSheet/Ledger/ship-sheet-ledger.json`, inside your project. It is a plain JSON file with a schema version, designed to be committed to version control with the rest of the project. Nothing is stored in the Library folder, and nothing leaves your machine: no account, no cloud, no telemetry.

## How do I delete or reset my ledger?

ShipSheet deliberately ships no one-click reset: a provenance record is exactly the data a reset button must never make easy to lose. If you are sure, first export a backup with **Export Ledger (CSV)** or **Export Ledger (JSON)** in Setup & Health, then delete `Assets/ShipSheet/Ledger/ship-sheet-ledger.json` yourself. Running **Run Setup / Verify Install** afterwards creates a fresh, empty ledger.

## What happens when I rename or move an asset?

Records are keyed by the asset's Unity GUID, which survives moves and renames. ShipSheet refreshes the cached path on the record and keeps every provenance field as it was.

## What happens when I delete an asset?

The record is never silently deleted. It is marked orphaned and appears in the **Review Queue**, where you choose to remove the record or keep it and re-point it at a replacement asset. A shipped-then-deleted asset is exactly what a disclosure audit asks about, so the history stays yours to resolve.

## Valve changed the rules — what happens to my template?

Disclosure templates in ShipSheet are versioned and dated in the product: the window and every export header show which Valve rules a draft is based on (the v1 template reads "Steam disclosure template — based on Valve rules as of 17 January 2026"). When Valve changes the rules, the answer is a template update to this package — your ledger, records, and exports are untouched, and a stale template always looks stale rather than silently passing as current.

## Does ShipSheet detect AI-generated content for me?

No. ShipSheet records what you declare: the disclosure draft is generated from records whose AI involvement you set, and unrecorded content is surfaced by the red-flag scan instead of being guessed at.

## Does ShipSheet submit anything to Steam?

No. ShipSheet generates a draft text file. You read it, edit it, and paste it into Steamworks yourself. ShipSheet holds no Steam credentials and contains no Steamworks connection.

## Which Unity versions and platforms are supported?

Unity **2022.3 LTS** and **Unity 6**. ShipSheet is editor-only tooling for **Windows and macOS** editors and adds nothing to your player build. There are **no third-party dependencies**.

## Does running the scan change anything in my project?

No. The [red-flag scan](./red-flag-scan) is read-only: it evaluates your records and writes only its report exports. It never writes to the ledger or to any asset. Fixing a flag is always your own edit to the record, via the flag's **Open Record** action.

## Why did an asset get only one flag when two rules seem to apply?

Each asset carries at most one flag — the most fundamental problem first: **RF-1** (no record) before **RF-3** (font evidence, for fonts) before **RF-2** (non-commercial licence) before **RF-4** (missing credit text). Clear the flag shown, re-run the scan, and the next applicable rule — if any — is reported then. The precedence is defined on the [Red-Flag Rules](./red-flag-rules) page.

## Does ShipSheet cover my code packages and plugins?

No — by design. UPM packages, DLLs and plugin licences are out of scope; ShipSheet covers content only: art, models, textures, audio, fonts, video, animations, materials, and text content. See [What v1 Is Not](./what-v1-is-not).
