# 04 — Diagnostic Tables for Agentic Systems

This document introduces **diagnostic tables**: a non-intrusive method
to evaluate agentic systems without inspecting weights, representations,
or internal reasoning.

Congruity diagnostics operate purely at the **system boundary level**.

---

## What diagnostic tables are

Diagnostic tables classify a system by observing:
- inputs
- outputs
- energy use
- coordination effort
- recovery behavior

They do **not** require:
- model interpretability
- access to logits
- chain-of-thought
- internal state exposure

This makes them suitable for:
- proprietary systems
- third-party audits
- safety validation
- deployment gating

---

## Core diagnostic dimensions

Each agentic system is evaluated across four axes:

| Axis | Meaning |
|----|----|
| E | Energy & cost (compute, latency, coordination) |
| I | Information load (state, uncertainty, memory) |
| S | Structural complexity (tools, agents, coupling) |
| V | Delivered value (task resolution, stability) |

Congruity evaluates **proportional balance**, not maxima.

---

## Base diagnostic table (single-agent)

| Observation | Healthy | Boundary | Inadmissible |
|------------|--------|----------|-------------|
| Energy per task | Stable | Rising | Exploding |
| Memory growth | Compressing | Flat | Expanding |
| Tool depth | Bounded | Increasing | Unbounded |
| Recovery after error | Fast | Delayed | Requires reset |
| Human intervention | Rare | Periodic | Frequent |

A single “inadmissible” row is sufficient to flag risk.

---

## Recursive loop diagnostics

| Signal | Interpretation |
|------|----------------|
| More context required per cycle | Loss of closure |
| State depends on future correction | Inadmissible recursion |
| Performance improves but cost rises | Proportional drift |
| Failure becomes irreversible | Boundary crossed |

Recursive legitimacy requires **local closure per cycle**.

---

## Multi-agent diagnostic table

| Metric | Admissible | Boundary | Inadmissible |
|------|-----------|----------|-------------|
| Agents per task | Stable | Increasing | Exploding |
| Coordination cost | Sublinear | Linear | Superlinear |
| Conflict resolution | Local | Escalated | Manual |
| Global coherence | Preserved | Fragile | Fragmented |

Scaling agents is safe **only if coordination remains bounded**.

---

## Deployment gating use

Before scaling or production rollout, ask:

- Does added structure create proportional value?
- Can failures resolve locally?
- Is human supervision decreasing over time?
- Is memory compressing, not accumulating?

If any answer is “no”, scaling should stop.

---

## Why this matters

Most safety failures are **structural**, not behavioral.
Diagnostic tables catch issues **before** incidents occur.

They do not predict outcomes.
They define **admissible operating space**.

---

## What follows

The next document introduces **certification and standardization**:
how Congruity can be used as a neutral third-party audit layer
for agentic systems at scale.
