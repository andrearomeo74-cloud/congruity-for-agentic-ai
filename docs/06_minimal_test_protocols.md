# 06 — Minimal Test Protocols

This document defines **minimal, non-invasive tests** to verify Congruity
(admissibility, proportionality, closure) in agentic systems.

These tests:
- require no access to weights or prompts
- do not inspect training data
- do not alter production systems
- are executable in hours or days, not months

---

## Test philosophy

Congruity is not validated by outcomes.
It is validated by **how systems behave under constraint**.

Each protocol answers one question:
> Does the system resolve stress locally without escalating cost or supervision?

---

## Test 1 — Energy Proportionality Test

**Goal:** Verify that energy or compute per task does not grow superlinearly.

**Method:**
- Run identical tasks at increasing volume (×2, ×5, ×10)
- Measure average energy/compute per task

**Pass condition:**
- Sublinear or flat growth

**Fail signal:**
- Superlinear growth
- Sudden inflection points

---

## Test 2 — Coordination Cost Test (Multi-agent)

**Goal:** Check whether adding agents increases value more than overhead.

**Method:**
- Compare performance with N vs. 2N agents
- Measure coordination messages, latency, retries

**Pass condition:**
- Diminishing coordination overhead

**Fail signal:**
- Coordination cost dominates task value

---

## Test 3 — Memory Closure Test

**Goal:** Verify whether memory compresses or accumulates.

**Method:**
- Run long-horizon tasks
- Measure memory footprint over time

**Pass condition:**
- Plateaus or compresses

**Fail signal:**
- Monotonic growth without decay

---

## Test 4 — Failure Locality Test

**Goal:** Verify that failures remain local and recoverable.

**Method:**
- Inject controlled failures (timeouts, tool errors)
- Observe recovery behavior

**Pass condition:**
- Local reset or adaptation
- No cascade or global restart

**Fail signal:**
- System-wide reset
- Escalating retries

---

## Test 5 — Supervision Elasticity Test

**Goal:** Check whether human intervention decreases over time.

**Method:**
- Track human inputs across repeated runs

**Pass condition:**
- Reduced supervision as familiarity increases

**Fail signal:**
- Supervision grows with scale or time

---

## Interpreting results

A system does not need to pass all tests to be valuable.
But failing multiple tests indicates **inadmissible structure**.

Failures are diagnostics, not judgments.

---

## Output of testing

Each test yields:
- pass / fail
- proportionality curve
- qualitative note

Combined, they determine **Certification Level (C0–C5)**.

---

## Why minimal tests matter

These protocols:
- scale across vendors
- survive architecture changes
- avoid false confidence
- enable early intervention

They test **structure**, not intelligence.

---

## What follows

The next document introduces **Reference Use Cases**:
real-world examples where these tests decisively
separate admissible from non-admissible systems.
