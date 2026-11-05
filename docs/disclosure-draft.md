---
layout: default
title: Disclosure Draft
nav_order: 10
description: "The Steam Generative-AI disclosure draft ShipSheet generates from your ledger: pre-generated and live-generated sections, the dated template, and the .txt/.md output pair."
---

# The Disclosure Draft
{: .no_toc }

## Your Steam AI disclosure, written from the record — not from memory
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## What gets generated

**Generate Disclosure Draft** (Disclosure & Credits section) builds the draft from your [ledger records](./the-ledger), following the shipped template — in v1, `steam-disclosure-2026-01`, headed:

> *"Steam disclosure template — based on Valve rules as of 17 January 2026"*
>
> *"This is a draft to review and paste into Steamworks. Valve judges the game, not this form. ShipSheet reports what your records say. It is not legal advice."*

The draft has the survey's two sections:

- **Pre-generated Content** — one line per record whose AI involvement is `PreGenerated`: the asset's name, the tool that generated it (the record's `sourceName`), and where it appears in the game, taken from the record's notes.
- **Live-generated Content** — one line per `LiveGenerated` record: the feature's name, the tool behind it, and what it generates, from the record's notes.

If the ledger records no AI-generated content, the draft carries the same header and states: *"This project records no AI-generated content in its ShipSheet ledger."*

## The sample's draft, verbatim

Generated from the [SampleHarbour](./sampleharbour) sample ledger during verification:

```text
Pre-generated Content:
The following content assets were created with generative AI tools prior to release:
- Menu Theme (Suno v4): Main menu music theme, generated with an AI music tool and trimmed in-house.
- Poster Texture Set (Midjourney v6): Poster textures on the harbour warehouse walls, generated with an AI image tool.

Live-generated Content:
The following features generate content using AI tools during live gameplay:
- Live Portrait Generator (PortraitGen Live API): NPC portraits generated during gameplay by the runtime portrait service.
```

![The Disclosure & Credits section, with the generated draft]({{ "/assets/images/disclosure.png" | relative_url }})

## The section, as you use it

The **Disclosure & Credits** section shows the project name (a [setting](./settings) the draft carries), the dated template line, and both Generate actions. After generating, the section previews the output read-only, with **Open File** and **Copy**, and a generation report line: how many entries were included — and which records were excluded, and why.

## Output files

One action writes the draft twice, into `Assets/ShipSheet/Exports/` (see [Exports & Files](./exports-and-files)):

- **Plain text (`.txt`)** — the Steamworks paste target.
- **Markdown (`.md`)** — your team record.

## What the draft cannot contain

The template itself states it: *"This draft is generated from the content recorded in this project's ShipSheet ledger. Content that is not recorded does not appear."* ShipSheet does not detect AI content for you — it generates from what you declared. That is why the [Review Queue](./backfill-and-review-queue) habit matters: an AI asset with no record is invisible to the draft, and visible instead to the [scan](./red-flag-scan) as [RF-1](./red-flag-rules).

## Templates are dated, on purpose

Disclosure templates in ShipSheet are versioned and dated in the product: the window and every export header show which Valve rules a draft is based on. When Valve changes the rules, the answer is a template update to this package — your ledger, records, and exports are untouched, and a stale template always looks stale rather than silently passing as current.
