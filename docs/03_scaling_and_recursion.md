# 03 — Scaling, Recursion, and Silent Failure

This document explains why most agentic systems fail **after** apparent success.
The failure is not accuracy or capability.
It is **loss of admissible closure under scale and recursion**.

Congruity treats scaling as a boundary problem, not a performance problem.

---

## Why scaling breaks agents

As agents scale, three pressures increase nonlinearly:

- **Energy (E):** compute, latency, coordination cost
- **Information (I):** state explosion, uncertainty accumulation
- **Structure (S):** tool chains, dependencies, agent-agent coupling

Value (V) often grows sublinearly.
This creates proportional drift.

When proportionality breaks, the system appears to work — until it doesn’t.

---

## Recursion vs iteration

Recursion is not repetition.
It is **self-reference with state carryover**.

A recursive agent must:
- Compress prior state
- Preserve closure
- Avoid exporting unresolved decisions

Iteration without compression is not recursion.
It is deferred instability.

---

## Silent failure modes

Common failure signatures under scale:

- Growing tool depth per task
- Increasing memory without compression
- More agents required to maintain the same output
- Rising human intervention masked as “supervision”
- Improved benchmarks with worse system health

These are **boundary violations**, not bugs.

---

## Admissible recursion

A recursion loop is admissible only if:

- Each cycle closes locally
- State complexity does not monotonically increase
- Added structure produces proportional value
- Failure modes are reversible

If recursion requires future correction, it is inadmissible.

---

## Multi-agent amplification

Adding agents does not increase intelligence linearly.

Without admissibility checks:
- Coordination cost dominates
- Information coupling explodes
- Local closures conflict globally

Congruity treats multi-agent systems as **coupled dissipative structures**.
They must satisfy closure both locally and globally.

---

## Non-monotonic legitimacy

A system can move from:
Admissible → Boundary → Inadmissible  
**without changing behavior**, only scale.

This is why “it worked before” is not evidence.

---

## Diagnostic signals

Early indicators of inadmissible scaling:

- Value per unit energy decreases
- Coordination effort rises faster than throughput
- Memory growth replaces compression
- Decisions depend on context accumulation rather than resolution

These signals appear **before** catastrophic failure.

---

## What follows

The next document introduces **diagnostic tables**
to evaluate admissibility across agents, tools, and loops
without inspecting internal representations.
