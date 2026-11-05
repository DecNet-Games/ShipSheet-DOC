---
layout: default
title: Home
nav_order: 1
description: "ShipSheet keeps one provenance record for every content asset in your Unity project — and turns it into your Steam AI disclosure draft, credits block and red-flag report at ship time."
permalink: /
---

# ShipSheet — Content Provenance Ledger
{: .fs-9 }

One record, kept as you work, produces the three documents submission week demands.
{: .fs-6 .fw-300 }

[Getting Started](./docs/getting-started){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 } [Installation](./docs/installation){: .btn .fs-5 .mb-4 .mb-md-0 }

![ShipSheet Home: the ledger, with every content asset recorded]({{ "/assets/images/ledger.png" | relative_url }})

---

## Submission week asks two questions most projects answer from memory

Steam's content survey asks every releasing game what AI-generated content it contains — and where everything else came from. Valve rewrote the Generative-AI disclosure rules in January 2026, and the standard rejection stories all have the same shape: the survey does not match the build, the disclosure is too vague, an asset raises a rights concern.

Most projects answer from memory, in submission week, because the record was never kept. **ShipSheet keeps it** — inside the Unity Editor, as assets enter your project, not reconstructed at ship time.

## One ledger, three documents

1. **Record** — every art pack, audio file, font and AI generation gets a [ledger record](./docs/the-ledger): what it is, where it came from, its licence, its credit line. An [import hook](./docs/backfill-and-review-queue) catches assets as they arrive; backfill covers what is already in the project.
2. **Scan** — the [red-flag scan](./docs/red-flag-scan) checks your own records against [four rules](./docs/red-flag-rules) and names the asset and the fix: an unrecorded asset in the build, a non-commercial licence in a commercial project, a font without verifiable licence evidence, an attribution the licence requires but the record is missing.
3. **Generate** — the [Steam disclosure draft](./docs/disclosure-draft) in the current survey's shape (pre-generated and live-generated sections) and the [credits block](./docs/credits-block), generated from the recorded credit lines exactly as recorded.

![The scan landing: the Dockside Ambience Loop flagged by name]({{ "/assets/images/flag-beat.gif" | relative_url }})

<video controls preload="metadata" style="max-width: 100%">
  <source src="{{ "/assets/videos/demo.mp4" | relative_url }}" type="video/mp4">
  Your browser does not support the video tag. The same loop — records, scan, disclosure, credits — is documented step by step in the Quick Start.
</video>

---

## Proven on the included sample

The Ledger Sample Project ships in the package — the SampleHarbour scene with eight content assets already recorded in a pre-filled ledger, and one planted problem:

| Measured on the sample | Result |
| :--- | :--- |
| Sample ledger | **8 records, all recorded** |
| The planted problem | **Dockside Ambience Loop** — recorded CC BY-NC 4.0 (non-commercial) in a project set to ship commercially |
| Red-flag scan | Flags it **by name**, with the fix written out: replace it with a commercially licensed alternative, or obtain a commercial waiver |
| Disclosure draft | Pre-generated section names **Menu Theme (Suno v4)** and **Poster Texture Set (Midjourney v6)**; live-generated names **Live Portrait Generator (PortraitGen Live API)** |
| Credits block | "Dockside Ambience Loop by Harbour Sounds (CC BY-NC 4.0)" and "Harbour Sans by Harbour Type Co (OFL 1.1)" — exactly as recorded |
| Full flow, window open to every section exercised | **56.3 seconds** |

Walk it yourself in the [SampleHarbour](./docs/sampleharbour) page, or start with the [Quick Start](./docs/quick-start).

---

## Kept honest, on purpose

- **Drafts and records only** — ShipSheet never connects to Steamworks, holds no Steam credentials, and submits nothing. You read the draft, edit it, and paste it into Steamworks yourself.
- **Your records, reported** — the scan reports what your records say. It does not verify that a recorded licence is genuine, and it is not legal advice. The full boundary list is [What v1 Is Not](./docs/what-v1-is-not).
- **Local and quiet** — the ledger is a plain JSON file inside your project (`Assets/ShipSheet/Ledger/ship-sheet-ledger.json`), designed to be committed to version control. No account, no cloud, no telemetry. Editor-only: nothing from this package ships into a player build.
- **Compatible** — Unity **2022.3 LTS** and **Unity 6**. No third-party dependencies.

> **Pro Tip:** Run the red-flag scan whenever a new pack, font or AI generation enters the project — not just at ship time. A flag caught the week the asset arrives is a two-minute fix; the same flag caught in submission week is a schedule problem.

---

## Start here

- [Getting Started](./docs/getting-started) — the core concepts in five minutes
- [Installation](./docs/installation) — Asset Store install and one-click setup
- [Quick Start](./docs/quick-start) — the full loop on the sample, then on your own project
- [Red-Flag Rules](./docs/red-flag-rules) — RF-1 to RF-4, exactly what each one means
- [Support](./docs/support) — email and community
