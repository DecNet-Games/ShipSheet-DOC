---
layout: default
title: Troubleshooting
nav_order: 17
description: "ShipSheet troubleshooting: an existing ledger kept by Open Samples, a scan that checks nothing, missing disclosure entries, missing credit lines, and the docs-missing warning."
---

# Troubleshooting
{: .no_toc }

## Symptom → cause → what to do
{: .no_toc .text-delta }

Every behaviour below is the product working as documented — the fix is in how the record or the project is set up, not in the tool.

---

## Open Samples kept my existing ledger — the sample's eight records are not what I see

**By design.** Setup never overwrites an existing ledger, and Open Samples puts the sample's pre-filled ledger in place only where none exists. If your project already has a ledger, the sample scene opens against *your* records.

**Do this:** rehearse the sample path in a fresh project with no ledger — or, in your own project, first back up with **Export Ledger (JSON)** in Setup & Health, then move your ledger aside yourself and run **Run Setup / Verify Install**. Your exported backup is your way back.

## The scan ran but checked 0 assets — or a shipped asset was not flagged

**Check the scope first.** The default scope is *build-included content*: dependencies of the **enabled** scenes in Build Settings, plus content under `Resources` folders and `StreamingAssets`. An asset outside every build scene (and outside `Resources`/`StreamingAssets`) is not in the default scope. Code and other out-of-scope assets are never counted or flagged at all.

**Do this:** confirm the scene containing the asset is in Build Settings and enabled — or switch **Scan scope** to **whole project** in [Settings](./settings) for a full pass, and re-run. Also check the asset is content (art, audio, fonts, textures…), not code.

## A deleted asset's record is still in the ledger

**By design.** Deleting an asset never deletes its record: the record is marked *orphaned* and waits in the **Review Queue**. A shipped-then-deleted asset is exactly what a disclosure audit asks about.

**Do this:** resolve it in the Review Queue — remove the record, or keep it and re-point it at the replacement asset. Orphaned records are skipped by the [scan](./red-flag-scan) until you decide.

## The disclosure draft is missing an AI asset I used

**The draft contains only what records declare.** A generated line exists only for a record whose **AI involvement** is set (`PreGenerated` or `LiveGenerated`), with the tool in `sourceName` and the where-it-appears note in `notes`. Unrecorded content does not appear in the draft at all — the template says so in its own header.

**Do this:** find the asset's record in the [Ledger](./the-ledger) (or its *Needs Review* entry in the [Review Queue](./backfill-and-review-queue)), set its AI involvement, source and notes, and regenerate. If the asset has no record, the [scan](./red-flag-scan) will already be flagging it [RF-1](./red-flag-rules).

## A credit line is missing from the credits block

**The block prints records that require attribution *and* carry the line.** If `attributionRequired` is set but `attributionText` is empty, there is nothing to print — and the scan flags exactly that as [RF-4](./red-flag-rules).

**Do this:** open the record from the flag (**Open Record**), paste the licence's credit line into `attributionText` verbatim, and regenerate the [credits block](./credits-block).

## A font is flagged RF-3 even though its licence is fine

**RF-3 is about evidence, not guilt.** A font is flagged when its recorded origin is `Unknown`, its **evidence link is empty**, or its recorded source matches the package's bundled mirror-site list — because a font whose licence evidence cannot be produced is the risk, whatever the licence says.

**Do this:** set the record's origin and source accurately and attach the licence evidence (purchase proof, licence file or receipt reference) in `evidenceLink`, then re-run the scan. See [RF-3](./red-flag-rules).

## **Tools → Decnet Games → ShipSheet → Documentation** logs "Documentation is missing from the package"

**The import is incomplete.** The Documentation menu item opens the quick-start from the package's `Documentation~` folder and logs that warning when the file is not there.

**Do this:** re-import the full package from Package Manager (**My Assets**) — do not import a partial file selection. The same four shipped pages (quick-start, ledger-fields, FAQ, "what v1 is not") are also the basis of this site, starting at [Quick Start](./quick-start).
