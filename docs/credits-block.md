---
layout: default
title: Credits Block
nav_order: 11
description: "The ShipSheet credits block: recorded attribution lines, exactly as recorded, grouped by origin class — generated from the same ledger as the disclosure."
---

# The Credits Block
{: .no_toc }

## The credit lines your licences require, exactly as recorded
{: .no_toc .text-delta }

---

## What gets generated

**Generate Credits Block** (Disclosure & Credits section) assembles the credits from your [ledger records](./the-ledger): for every record whose licence **requires attribution**, it prints the record's `attributionText` — **exactly as recorded, nothing retyped** — grouped by the record's origin class. The generator also reports attribution gaps: a record that requires attribution but has no credit text is the [RF-4](./red-flag-rules) condition, and the [scan](./red-flag-scan) flags it until the line is entered.

The block is a text export and an in-window preview. It is not a credits screen — your game's credits interface is your own system (see [What v1 Is Not](./what-v1-is-not)).

## The sample's block, verbatim

Generated from the [SampleHarbour](./sampleharbour) sample ledger during verification:

```text
ShipSheet — Credits & Attributions

CC or Stock Sources:
Dockside Ambience Loop by Harbour Sounds (CC BY-NC 4.0)
Harbour Sans by Harbour Type Co (OFL 1.1)
```

Two records in the sample require attribution; both lines appear word-for-word as their records carry them. Note what the block demonstrates about the ledger's honesty: the Dockside Ambience Loop's credit prints even though the same record carries the sample's [RF-2](./red-flag-rules) flag — the credits block reports the record; clearing the flag is a licensing decision the scan surfaces and you make.

![The credits block preview in the Disclosure & Credits section]({{ "/assets/images/credits.png" | relative_url }})

## Output

The generated block is written to `Assets/ShipSheet/Exports/` alongside the disclosure pair (see [Exports & Files](./exports-and-files)), and previewed in the section with **Open File** and **Copy** — ready to paste into your own credits screen, store page, or third-party notices file.

## Keeping it complete

A credits block can only print what records carry. The working habit:

1. When you confirm a record in the [Review Queue](./backfill-and-review-queue), check whether its licence requires attribution.
2. If it does, paste the licence's credit line into `attributionText` at that moment — from the licence, not from memory.
3. Run the [scan](./red-flag-scan) before you ship: any record still missing its line is flagged [RF-4](./red-flag-rules) by name.
