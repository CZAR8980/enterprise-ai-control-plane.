# Enterprise AI Control Plane Architecture

> A deterministic 5-phase control plane for high-stakes enterprise AI agents. Designed to prevent probabilistic drift, race conditions, and hallucinated financial/legal execution while preserving unit economics.

---

## Architectural Blueprint Overview

![Operational Blueprint](./operational-blueprint.png)

### Core Control Pillars

* **Risk-Tiered Execution & Short-Circuiting (`N_01.3`):** Dynamic routing upfront. Low-stakes requests (Tier 0) bypass heavy evaluation for direct execution; Tier 1 uses conditional validation; Tier 2 enforces full 5-phase containment.
* **Air-Gapped Factual Grounding Referee (`N_03.5`):** Secondary referee model evaluates final output claims against raw retrieved chunks with **zero visibility** into generator reasoning or system prompts.
* **Continuous Scoring & Closed-Loop Calibration (`N_00.1` / `N_05.4`):** Continuous vector similarity and entailment scores feed into telemetry loops to calibrate versioned policy tables, eliminating threshold rot.
* **Risk-Adjusted Settlement Buffer (`N_04.5`):** Dwell times scale dynamically ($0\text{s}$ to $24\text{h}$). Re-checks account state, dispute flags, and balance availability atomically immediately prior to API settlement.
* **Observability Spine for ROI (`N_00.1`):** Tracks prevented losses, token expenditure, latency SLAs, and human review hours to quantify platform ROI in real time.
* **Anti-Rubber-Stamping Human Oversight (`N_05.3` / `N_05.5`):** Tracks reviewer velocity ($<5.0\text{s}$ flags), approval drift ($>98\%$), and forces mandatory 5% random secondary sampling.

---

## Regulatory & Compliance Mapping

![Compliance Mapping](./compliance-mapping.png)

Every node in Phases 1–4 maintains isolated code boundaries to map cleanly against regulatory audit frameworks:
* **EU AI Act:** Article 9 (Risk Management), Article 12/15 (Record-Keeping & Logging), Article 14 (Human Oversight).
* **SOC 2 Type II:** CC6.1 (Logical Access), CC6.8 (Processing Integrity), CC7.2 (Operational Monitoring).
* **NIST AI RMF:** Govern 4.1, Measure 2.3.

---

## Circuit Breakers & Exception Dictionary

![Exception Dictionary](./exception-dictionary.png)

Upstream failures route directly into four terminal Phase 5 queues using normalized reason codes:
* **`N_05.1` Technical Exception Queue:** Catches schema drifts, API timeouts, and lock exhaustion.
* **`N_05.2` Account & Policy Queue:** Handles ceiling breaches and pre-settlement state drift.
* **`N_05.3` Domain SME Triage Queue:** Manages gray-band confidence drops and low-grounding claims.
* **`N_05.5` 2-Person Approval Queue:** Handles high-value overrides ($>\$10\text{k}$) and reviewer drift alarms.

---

## License

This architecture is released under the **MIT License**. Free to use, modify, and implement for commercial or open-source projects.
