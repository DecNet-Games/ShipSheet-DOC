---
layout: default
title: Installation
nav_order: 3
description: "Install ShipSheet from the Unity Asset Store and run the one-click setup. ShipSheet is sold exclusively through the Unity Asset Store."
---

# Installation
{: .no_toc }

## Asset Store only
{: .no_toc .text-delta }

> **ShipSheet is sold exclusively through the Unity Asset Store** (publisher: Decnet Games). It is not distributed for free on GitHub or anywhere else — this site is the product's documentation, not a download. If you obtained a copy of ShipSheet from any other source, it is not an official copy.

1. TOC
{:toc}

---

## Requirements

- **Unity 2022.3 LTS** or **Unity 6**.
- An Editor on **Windows or macOS**. ShipSheet is editor-only tooling: it adds nothing to your player build.
- **No third-party dependencies.** Nothing else to install, and no network connection needed at run time — the ledger lives in your project and nothing leaves your machine.

## Install from the Asset Store

1. Purchase ShipSheet on the Unity Asset Store under the Unity ID you use for your projects.
2. In the Unity Editor, open **Window → Package Manager**, switch the Packages filter to **My Assets**, find **ShipSheet**, and choose **Download**, then **Import**.
3. Import the full package. The package includes the ShipSheet editor tooling, the Ledger Sample Project (SampleHarbour), and the documentation set — the same quick-start, ledger-fields reference, FAQ and "what v1 is not" pages that also live in the package's `Documentation~` folder.

## Run Setup (once)

1. Open the Home window: **Tools → Decnet Games → ShipSheet → ShipSheet Home**.
2. Click **Run Setup / Verify Install** (welcome block, or the Setup & Health section).
3. Setup creates `Assets/ShipSheet/Ledger/ship-sheet-ledger.json` and the settings asset — **and never overwrites an existing ledger**. If a ledger already exists, setup verifies it and reports what it found in plain language.

![The setup report in the Setup & Health section]({{ "/assets/images/setup-report.png" | relative_url }})

Run Setup again at any time — it is safe and idempotent. The [Setup & Health section](./exports-and-files) is also where the ledger exports live.

## Verified in a clean project

The shipped package was verified in a brand-new Unity 6000.5.4f1 project: the package **installs, compiles with zero errors, and the Home window opens and runs** — no project content or configuration of ours present. The full interactive pass (sample ledger, scan, disclosure, credits) was run against the product's own projects and is documented in the [Quick Start](./quick-start) and [SampleHarbour](./sampleharbour) pages.

## Updating

Updates are delivered through the Asset Store like any other package: re-download the new version in Package Manager (**My Assets**) and import it over the existing install. Your ledger is a project file under `Assets/ShipSheet/` — it is not part of the package folder and is untouched by an update.

## Uninstalling

Delete the ShipSheet package from your project (Package Manager, or the package folder for an embedded install). The data ShipSheet created stays where it always lived — under `Assets/ShipSheet/` in your project (ledger, settings, exports) — as ordinary project files you can keep as your record or delete yourself. ShipSheet deliberately ships no one-click ledger reset; see the [FAQ](./faq).
