---
layout: default
title: Settings
nav_order: 13
description: "ShipSheet's four project settings: ships commercially, scan scope, project name, and disclosure template selection — stored in Assets/ShipSheet/Settings."
---

# Settings
{: .no_toc }

## Four settings, all in one project asset
{: .no_toc .text-delta }

---

ShipSheet's project configuration is a single settings asset — `Assets/ShipSheet/Settings/ShipSheetSettings.asset` — created by [setup](./installation) alongside the ledger. It carries exactly four settings:

| Setting | Default | What it controls |
| :--- | :--- | :--- |
| **Ships commercially** (`shipsCommercially`) | On | Whether this project ships commercially. The [RF-2](./red-flag-rules) rule is evaluated against it: a record whose licence is non-commercial is only a flag while the project ships commercially. |
| **Scan scope** (`scanScope`) | Build-included content | Which assets the [red-flag scan](./red-flag-scan) evaluates: the dependencies of enabled Build Settings scenes plus `Resources` and `StreamingAssets` content — or, in **whole-project** mode, every in-scope content asset in the project. |
| **Project name** (`projectName`) | Empty | The name the generated documents carry. Also editable directly in the [Disclosure & Credits](./disclosure-draft) section, which writes it back to the same setting. |
| **Template selection** (`templateSelection`) | `steam-disclosure-2026-01` | Which dated disclosure template the [disclosure generator](./disclosure-draft) uses. The v1 template is based on Valve rules as of 17 January 2026; the window and every export header show the template's date, so a stale template always looks stale. |

## Defaults are the honest configuration

The defaults are set up so a fresh install behaves the way the documentation describes: the project is treated as shipping commercially (so licence problems surface rather than hide), the scan covers what the build includes (so flags are about what actually ships), and the current dated template is selected. Change a setting only when the project's facts differ — for example, a genuinely non-commercial project turns **Ships commercially** off, and with it the RF-2 rule, rather than editing records to silence flags.
