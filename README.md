# Pantry Perth — Web Ecosystem Triage & Handover

This repository contains the stabilized, audited digital assets for Pantry Perth, a registered Australian community charity. Following an incomplete development phase by a prior volunteer, a comprehensive engineering triage has been executed to resolve high-severity user experience defects, structural compilation failures, and API integration vulnerabilities.

The core frontend layout, dynamic React features, and data-driven counter assets have been stabilized and configured for local staging and validation loops.

---

## 1. System Architecture & Repository Topology

The project ecosystem is broken down into a decoupled architecture, combining static public-facing presentation layers with a component-driven transactional utility framework:

```text
├── assets/
│   ├── css/style.css       # Core presentation layer (Tier 1 UI stabilization)
│   └── js/stock.js         # Pantry inventory tracking module (Tier 2 API fallback integration)
├── donate-widget/          # Isolated React utility bundle (Built with Vite)
│   ├── src/components/     # Transactional state UI components
│   └── src/main.jsx        # Component execution & asset ingestion layer (Tier 3 metadata tagging)
├── ai-conversations/       # Verification logs demonstrating strategic tool interaction
│   ├── 01-ui-accessibility.md
│   ├── 02-api-defensive-parsing.md
│   └── 03-asset-injection.md
├── audit-memo.md           # Executive governance and deployment readiness report
├── contribution-map.md     # Cross-reference documentation for version control history
└── index.html              # Main landing page interface
```
## 2. Assessment Handover Documentation Map
To review the specific strategic decisions, trade-offs, and implementation metrics required for this handover, please refer to the following local core documentation assets:

Executive Strategic Analysis: See /audit-memo.md for the comprehensive triage breakdown, business risk logs, and the conditional project relaunch recommendation.

Engineering Version History Mapping: See /contribution-map.md to review the architectural justifications, rejected technical paths, and associated local Git tracking references.

Verification Log Directory: See /ai-conversations/ to review raw, uncensored back-and-forth validation scripts demonstrating technical critique, tool constraints, and environment testing strategies.

## 3. Staging & Execution Configuration
Comprehensive environment configuration guides, local database recovery frameworks, and runtime troubleshooting playbooks are retained inside the dedicated technical onboarding documents provided in the package:

To initialize local database engines and host the web structures on a local sandbox workspace, refer to SETUP.md.

To bypass server caching anomalies or restore content pipelines during complex environment transitions, refer to RECOVERY.md.

## 4. Current Ecosystem Status Summary
Following the completion of the Phase 1 Triage cycle, core operations have been safely restored. Known downstream infrastructure constraints (including external WordPress endpoint coupling and mock merchant gateway placeholder environments) have been isolated and safely cataloged inside the project's Known Issues backlog for secondary phase scheduling. All primary interaction elements are stable, compilation-safe, and ready for validation review.
