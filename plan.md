# AdaMode Case Studies — Slide Restructure Overview

---

## Narrative Thread

> "One site. Three layers of AI. Each doing something the previous layer couldn't."

All three case studies anchor to the nuclear sector — two directly to **Sellafield**, one to **nuclear legislation** more broadly. This gives the talk a single through-line instead of three disconnected examples.

---

## Slide Structure

### ─── STAGE i: Autoregression ───────────────────────────

**[ Existing ] Listening to machines**
- Sliding window animation
- "last readings → next value"

**[ Existing ] Anomaly Detection in Practice**
- Strip chart interactive demo

**[ NEW ] AdaMode Case Study — Waste Vitrification Plant, Sellafield**

```
Problem     Highly Active Liquor (HAL) must be continuously processed into
            vitrified glass — one of Sellafield's highest priorities.
            Line blockages cause downtime; downtime means HAL backs up,
            a significant site hazard.

Approach    Anomaly detection + dynamic time warping on process plant
            sensor data via Ada Mode's Atom platform.
            Predict blockages before they manifest.

Outcome     Critical downtime events predicted with sufficient lead time
            for proactive intervention — substantial increase in plant
            availability and HAL throughput rate.

Constraint  500+ diverse facilities. Data stays on-site.
```

> *Callout → "Predict before it fails. The model comes to the data."*

---

### ─── STAGE ii: Small Language Model ─────────────────────

**[ Existing → Reformat ] Sellafield Condition Reports**

```
Problem     11,000 staff across 500+ facilities file free-text
            off-normal Condition Reports. Manual trend-coding
            is slow and inconsistent.

Approach    On-premises open-source SLM.
            One report in → structured trend code out.
            No cloud. Formally classified data.

Outcome     < 1 second per report at human-level accuracy.

Constraint  Security classification ruled out cloud
            before the question was asked.
```

> *Callout → "Deploy local or ship nothing."*

*Remove/condense duplicate Sellafield content currently in Part 3 (lines 1220–1249).*

---

### ─── STAGE iii: Large Language Model ────────────────────

**[ Existing ] Reading complex language at scale**
- llm-language animation (semantic decomposition)

**[ PULL FORWARD from Part 3 ] Nuclear Legislation Analysis**

```
Problem     SMR licensing requires cross-walking UK goal-setting
            obligations with US prescriptive rules.
            Manual expert reading: months of work.

Approach    LLM with enforced citation schema.
            Every answer must carry supporting_quote + citation.
            Null citation = no answer given.
            Judge LLM validates against expert ground truth.

Outcome     Cross-jurisdiction correspondences surfaced in seconds
            for expert review.

Constraint  Output is always a lead — never a conclusion.
```

> *Callout → "Enforced citation turns the model into a research assistant, not an oracle."*

*Remove/condense from Part 3 (lines 1023–1060).*

---

### ─── BRIDGE SLIDE (new) ──────────────────────────────────

**One pattern across all three**

| | Autoregression | Small LM | Large LM |
|---|---|---|---|
| **What it did** | Predicted WVP failure | Coded Condition Reports | Cross-walked legislation |
| **Key constraint** | Data never leaves site | No cloud option | Human always verifies |
| **Rule it demonstrates** | Least-privilege by default | Deploy local or not at all | Leads, never conclusions |

*Part 3's "Three Rules for Wednesday Morning" now arrives with context the audience has already lived through.*

---

## What Changes in slides.md

| Location | Change |
|---|---|
| After line 184 | Insert WVP autoregression case study slide |
| Lines 195–215 | Reformat Sellafield to case study card + callout |
| After line 244 | Insert nuclear legislation case study (moved from Part 3) + callout |
| After that group | Insert bridge slide |
| Lines 1023–1060 | Condense (now lives in Stage iii) |
| Lines 1220–1249 | Condense (now lives in Stage ii) |
