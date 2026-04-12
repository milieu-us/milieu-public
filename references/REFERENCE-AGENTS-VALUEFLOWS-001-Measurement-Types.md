# REFERENCE-AGENTS-VALUEFLOWS-001 - Measurement Types for Agent Work and Value Flows

- **ID:** REFERENCE-AGENTS-VALUEFLOWS-001
- **Status:** Working Draft
- **Created:** 2026-03-11
- **Updated:** 2026-04-11

## Intent
Provide a shared, minimal vocabulary for how human agents, AI agents, and system agents record measurements that inform value flows.

## Three Measurement Types

### 1) Boolean
**What it is:** A yes/no value.  
**Use for:** Pass/fail gates, presence/absence, completion flags.  
**Units:** None (but the meaning of “true” must be defined).

Examples: `reverted?`, `gate_passed?`, `decision_ratified?`

### 2) Unit Scale
**What it is:** A normalized scalar in the closed interval **[0, 1]** (“Unit Scale”).  
**Use for:** Weights, confidence, impact, risk, and other “how much” judgments that need to combine across contexts.  
**Units:** Unitless (meaning must be named, e.g., “confidence,” “impact”).

Examples: `confidence`, `impact`, `risk_before`, `risk_after`, `evidence_quality`

### 3) Quantity with Units
**What it is:** A numeric value with explicit units.  
**Use for:** Time, cost, compute, storage, counts, performance, and rates.  
**Units:** Always required (including compound units for rates).

Examples: `time_spent_minutes`, `usd_cost`, `build_time_seconds`, `storage_gb`, `pr_count`, `items_per_week`
