---
layout: default
title: SampleHarbour Sample
nav_order: 14
description: "The Ledger Sample Project: SampleHarbour's eight pre-recorded content assets, the planted RF-2 problem, and the two-minute path through scan, disclosure and credits."
---

# The SampleHarbour Sample
{: .no_toc }

## A harbour scene with a full ledger — and one planted problem
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## What is in the sample

The **Ledger Sample Project** ships in the package (Package Manager → ShipSheet → Samples → **Import**), or opens from the Home window's **Open Samples** quick action:

- **SampleHarbour.unity** — the harbour scene.
- **Content/** — the eight content assets: Harbour Props Pack, Seagull Calls, Dockside Ambience Loop, Menu Theme, Poster Texture Set, Live Portrait Generator, Harbour Sans Font, and Tutorial Voice Lines.
- **Ledger/ship-sheet-ledger.json** — the pre-filled ledger with one record per content asset.

Opening the samples never overwrites your own ledger: if your project already has one, setup keeps it by design — rehearse the sample's data in a project without a ledger, or export yours first (see [Troubleshooting](./troubleshooting)).

![SampleHarbour, as it ships]({{ "/assets/images/sample-hero.png" | relative_url }})

## The eight records

| Record | What it demonstrates |
| :--- | :--- |
| Harbour Props Pack | A recorded content pack asset. |
| Seagull Calls | A recorded audio asset with no flag. |
| **Dockside Ambience Loop** | **The planted problem:** recorded as **CC BY-NC 4.0** — a non-commercial licence — in a project set to ship commercially. The scan catches it by name as [RF-2](./red-flag-rules). Its credit line ("Dockside Ambience Loop by Harbour Sounds (CC BY-NC 4.0)") still prints in the [credits block](./credits-block), exactly as recorded. |
| Menu Theme | A **pre-generated** AI record (Suno v4) — appears in the disclosure draft's pre-generated section. |
| Poster Texture Set | A **pre-generated** AI record (Midjourney v6) — appears in the disclosure draft's pre-generated section. |
| Live Portrait Generator | A **live-generated** AI record (PortraitGen Live API) — appears in the disclosure draft's live-generated section. |
| Harbour Sans Font | A font with full licence evidence (OFL 1.1, "Harbour Sans by Harbour Type Co") — the contrast case for [RF-3](./red-flag-rules): no flag. |
| Tutorial Voice Lines | A recorded audio asset completing the set of eight. |

When the sample ledger is in place, the Ledger section header reads **"8 recorded — 1 need review — 0 unrecorded"** — the one *need review* row is the ledger file's own row, not a ninth content asset.

## The two-minute path

1. Open **Tools → Decnet Games → ShipSheet → ShipSheet Home**.
2. Click **Run Setup / Verify Install** — on the sample path, setup verifies the sample's shipped ledger instead of creating an empty one.
3. Open the **Ledger** section: eight records, all recorded.
4. Open **Red Flags** and click **Run Red-Flag Scan**: exactly one flag, the Dockside Ambience Loop, with the fix action written out.
5. Open **Disclosure & Credits** and click **Generate Disclosure Draft**: the pre-generated section names the Poster Texture Set and the Menu Theme; the live-generated section names the Live Portrait Generator. Click **Generate Credits Block**: the credit lines of the Dockside Ambience Loop and the Harbour Sans Font, exactly as recorded.

Measured during verification, the full flow — window open to every section exercised — took **56.3 seconds**. The [Quick Start](./quick-start) walks the same path and then continues into recording your own project.
