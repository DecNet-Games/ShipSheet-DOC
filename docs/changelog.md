---
layout: default
title: Changelog
nav_order: 18
description: "ShipSheet changelog: version 1.0.0, the initial release — provenance ledger, Steam disclosure draft generator, credits generator, and the four-rule red-flag scanner."
---

# Changelog
{: .no_toc }

All notable changes to the ShipSheet package are documented here. The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and the project adheres to Semantic Versioning. This page carries the package's shipped changelog.

---

## [1.0.0] — 2026-11-04

### Added

- Initial release of ShipSheet.
- Core provenance ledger data models and `schemaVersion: 1` storage format.
- GUID-persistent asset tracking surviving moves and renames.
- Silent background asset postprocessor for new and deleted assets.
- Steam Generative-AI disclosure draft generator based on Valve rules as of 17 January 2026.
- Origin-grouped in-game credits block generator with attribution gap reporting.
- Deterministic read-only red-flag audit scanner evaluating the four red-flag rules.
- Unified ShipSheet Home Editor window with status strip and quick actions.
- SampleHarbour demonstration project and documentation suite.
