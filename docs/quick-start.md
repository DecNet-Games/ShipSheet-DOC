---
layout: default
title: Quick Start
nav_order: 4
description: "From import to first success: the two-minute sample path, then recording your own project — backfill, review queue, scan, disclosure, credits."
---

# Quick Start
{: .no_toc }

## From import to first success in about ten minutes
{: .no_toc .text-delta }

Every action named here exists in the ShipSheet Home window under the same name. This page follows the product's shipped quick-start guide.

1. TOC
{:toc}

---

## The sample path (first success, about two minutes of clicking)

1. Open **Tools → Decnet Games → ShipSheet → ShipSheet Home**.
2. In the welcome block, click **Open Samples**. The Ledger Sample Project is imported, SampleHarbour opens, and the sample's pre-filled ledger is put in place (your own ledger, if you already have one, is never overwritten).
3. Click **Run Setup / Verify Install**. Setup verifies the install and the sample's shipped ledger, and reports what it found in plain language.
4. Open the **Ledger** section: eight records, all recorded.

   ![The sample ledger: eight records, all recorded]({{ "/assets/images/ledger.png" | relative_url }})

5. Open the **Red Flags** section and click **Run Red-Flag Scan**. Exactly one flag appears: the **Dockside Ambience Loop**, whose recorded licence is non-commercial while the project is set to ship commercially. The flag names the asset and the one action that clears it. Click its **Open Record** to land on the record in the Ledger.

   ![The flag, in full: asset, rule, fix]({{ "/assets/images/redflag-detail.png" | relative_url }})

6. Open **Disclosure & Credits** and click **Generate Disclosure Draft**. The draft's pre-generated section names the Poster Texture Set and the Menu Theme; its live-generated section names the Live Portrait Generator. Click **Generate Credits Block** to see the credit lines of the records that require them.

That is the whole product in one pass: one record produced the flag report and both documents. The [SampleHarbour](./sampleharbour) page catalogues the sample's eight records and what each one demonstrates.

## Recording your own project

1. Click **Run Setup / Verify Install** (welcome block or Setup & Health). This creates `Assets/ShipSheet/Ledger/ship-sheet-ledger.json` and the settings asset. It never overwrites an existing ledger.
2. Click **Backfill This Project** in the **Ledger** section. Every in-scope content asset without a record gets a *Needs Review* entry, grouped by folder in the **Review Queue**. Nothing is guessed: origin and licence start empty, with the folder name copied into Notes as a hint only.
3. Confirm each folder group in the **Review Queue** (origin, tool or source, and licence set once per group), or edit records one by one in the **Ledger**. New imports from now on join the Review Queue silently — imports are never interrupted.
4. Before you ship: **Run Red-Flag Scan**, then **Generate Disclosure Draft** and **Generate Credits Block** from the same records. The disclosure is written as plain text (the Steamworks paste target) and Markdown (your team record) in one action.
5. **Export Ledger (CSV)** and **Export Ledger (JSON)** in Setup & Health give you the full ledger in open formats at any time.

ShipSheet reports what your records say. It is not legal advice.
