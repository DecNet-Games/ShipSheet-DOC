---
layout: default
title: Support
nav_order: 19
description: "ShipSheet support: email Decnet Games, join the Discord community, and what to include when you report a problem."
---

# Support
{: .no_toc }

---

## Email

**support@decnetgames.com** — ShipSheet is made and supported directly by Decnet Games. The Home window's quick actions and the **Tools → Decnet Games → ShipSheet → Support** menu item open the same address.

## Community

Join the Decnet Games Discord: **https://discord.gg/P9wepz7NBW** — questions, records workflows from the field, and discussion with other ShipSheet users.

More Decnet Games tools live on the publisher page: **https://assetstore.unity.com/publishers/118262**.

## Reporting a problem — what to include

A good report gets a fast, useful answer. Please include:

1. **Your Unity version** (for example 2022.3 LTS or the exact Unity 6 build) and your Editor platform.
2. **What you ran** — setup, backfill, a scan, or a generator — and, for a scan, the **scope** in use (build-included or whole project) from [Settings](./settings).
3. **The JSON red-flag export** for scan questions. It is the machine-readable form of the report: scope, and per flag the asset GUID, name, rule code, description and fix action. The text report plus the flagged record's fields from the [Ledger](./the-ledger) answer most questions between them.
4. **The record in question.** If a flag or a missing draft line looks wrong, quote the record's fields — origin, source, licence, AI involvement, attribution — and say what you expected instead. Classification disagreements are exactly the reports that improve the [rules](./red-flag-rules).

Never send Steam credentials or account details — ShipSheet holds none and support will never ask for any.

## Before you write

- The [FAQ](./faq) answers the recurring questions — where the ledger lives, resetting it, renames and deletes, and template updates.
- [Troubleshooting](./troubleshooting) covers the by-design behaviours that look like faults: a kept ledger on Open Samples, a zero-asset scan, missing draft entries and missing credit lines.
- [What v1 Is Not](./what-v1-is-not) lists the deliberate v1 boundaries. If your request is outside them, it is still worth sending — boundaries move between versions, and user reports are how that happens — but it helps to know it is a boundary rather than a bug.
