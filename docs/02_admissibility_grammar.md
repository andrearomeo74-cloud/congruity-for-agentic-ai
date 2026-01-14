# 02 — The Admissibility Grammar

This document introduces the core grammar used by Congruity.
It is not an algorithm, policy, or optimization method.
It is a **structural filter** that determines whether a move can legitimately occur.

The grammar operates *before* planning, optimization, or reward.

---

## What admissibility is (and is not)

Admissibility is:

- Pre-behavioral  
- Pre-ethical  
- Pre-strategic  

It does **not** decide *what* the agent wants.
It decides *whether a move is allowed to exist* under current constraints.

An admissible move is one that can:
- Close structurally
- Preserve proportionality
- Avoid exporting instability

An inadmissible move may still be executable — but it is not legitimate.

---

## The four domains

Admissibility is evaluated across four coupled domains:

- **E — Energy:** physical, computational, temporal cost
- **I — Information:** state complexity, uncertainty, entropy
- **S — Structure:** coordination, coupling, dependencies
- **V — Value:** realized outcome, utility, effectiveness

A move is admissible only if proportionality holds across all four.

There is no privileged domain.
Violation in one breaks the move.

---

## Proportionality, not thresholds

Congruity does not rely on fixed thresholds.

Instead, it evaluates **relative proportionality**:

- Does added information justify added energy?
- Does increased structure produce commensurate value?
- Does coordination reduce entropy — or amplify it?

Admissibility is *relational*, not absolute.

---

## Closure

A move must be able to **close** without borrowing coherence.

Closure means:
- No deferred instability
- No hidden external dependencies
- No reliance on future correction

If closure cannot occur locally and reversibly, the move is inadmissible.

---

## False closure (revisited)

False closure is the appearance of completion without structural closure.

Signals of false closure include:
- “Good enough” answers that require human cleanup
- Tool chains that grow with each success
- Memory accumulation without compression
- Increasing coordination cost per decision

False closure is treated as a hard boundary.

---

## Boundary vs prohibition

Congruity does not prohibit actions.
It marks them as inadmissible.

An agent may still attempt them — but the system records a **boundary violation**.
This enables diagnostics, not enforcement.

---

## Non-commutativity

Admissibility is **non-commutative**:

- A move that is admissible early may become inadmissible later
- Reordering steps can break closure
- Scaling changes legitimacy

This is why static rules fail.

---

## Minimal output

The grammar produces one of three states:
- **Admissible**
- **Boundary**
- **Inadmissible**

No ranking.
No scoring.
No optimization.

Only structural legitimacy.

---

## What follows

The next document shows how this grammar interacts with
agent scaling, recursion, and multi-agent coordination
— where most silent failures emerge.
