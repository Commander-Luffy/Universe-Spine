# Dimensional Prime Theory → IPv8 Mapping

**Status:** DRAFT v0.1 — Falsifiable theory, not proven
**Date:** 2026-04-03
**Depends on:** DIMENSIONAL-PRIME-THEORY-v0.1.md, IPv8-STACK-DRAFT.md
**Classification:** Each claim marked AXIOM (assumed), DERIVED (from axioms), or TESTABLE (falsifiable prediction)

---

## 1. The I/CC/U/SU Quad

**[AXIOM]** At every level N, there are exactly 4 structural components:

| Component | Name | Role | Engineering | Control Theory |
|-----------|------|------|-------------|----------------|
| **I(N)** | Invariant | What MUST be true | Test suite / schema | Setpoint / reference signal |
| **CC(N)** | Contract | Feedback binding I to U | API contract / rate limit | Error signal + feedback law |
| **U(N)** | Unitary | What's PERMITTED | Interface / permissions | Control input / actuator |
| **SU(N)** | Special Unitary | The constructed system | Implementation | Plant output |

**Build order is forced:** I first (test), CC second (contract), U third (interface), SU last (implementation). SU(N) cannot be built without all three predecessors.

```
I(N) ──── CC(N) ──── U(N)
              │
           SU(N)
```

CC(N) is the **distributive constraint** — the "×" in S × U = SU. It's always phase-valued (a ratio, not an absolute). 45° = the stability boundary.

---

## 2. The I(N) Identity Hierarchy

**[DERIVED]** The strongest achievable notion of identity at SU(N) is constrained by generator count.

| N | N²-1 generators | I(N) | Framework | What it unlocks | Progression |
|---|-----------------|------|-----------|-----------------|-------------|
| 0 | -1 (pre-structural) | **PRIMITIVE** | (axiomatic floor) | Binary distinction. Exist/don't. | exist |
| 1 | 0 (static) | **PROPERTY** | Leibniz | Static observation. Compare attributes. | observe |
| 2 | 3 (dynamic) | **BEHAVIOR** | Bisimulation | Transition matching. Path-sensitive. | interact |
| 3 | 8 (full structure) | **IDENTITY** | Univalence (HoTT) | Equivalence = identity. | become |
| 4 | 15 (saturated) | **RELATION** | (inter-system) | Populations of identified things interact. | relate |

Each I(N) strictly subsumes I(N-1): identity implies behavioral equivalence implies property equality implies existence.

---

## 3. The Triple at Level 0

**[DERIVED]** At level 0 and ONLY at level 0, the three components split into distinct meanings:

| Component | At Level 0 | Meaning |
|-----------|-----------|---------|
| I(0) | PRIMITIVE | The binary distinction itself. The unit circle. τ is its invariant. |
| U(0) | AXIOM | The floor that primitives allow to exist. |
| SU(0) | UNDEFINED | Cannot be defined without ALL others defined. Requires infinity to resolve. |

Everywhere else I/U/SU appear redundant. At 0 they reveal themselves as fundamentally different things.

---

## 4. CC = The 4-Phase Chirality

**[AXIOM]** CC is always 4 phases of the unit circle:

```
    |i|          i = superposed / imaginary positive
     |
-1 ──O── 1      1 = forward / real positive
     |           -1 = reversed / real negative
   |-i|          -i = anti-superposed / imaginary negative
```

This is the **chirality tax** — every composition, every protocol, every header costs exactly 4 phases of CC overhead.

```
42 content primitives + 4 CC chirality = 46 total
```

This matches the ~46 universal phonetic base of human language (all distinguishable speech sounds across all languages).

---

## 5. Level 4 — The Three Emergences

**[TESTABLE]** At level 4, the I/U/SU triple produces three distinct emergences:

| Level 4 | What it is | What EMERGES | Why HERE |
|---------|-----------|--------------|---------|
| I(4) | Wavefunctions / Q | **TIME** | Superposition needs a basis for collapse → sequence → "when" |
| U(4) | Fields / Topology | **GRAVITY** | Permitted shape of spacetime. Curvature = what's allowed |
| SU(4) | Quantum Gravity | **ENTROPY** | Needs ALL above. Produces irreversibility |

CC at level 4 = **CAUSALITY**. c is phase (45° invariant in any time-space projection), not velocity. c² = CC = |causality| = the norm of the causal boundary.

**Falsifiable:** SU(4) cannot be solved until I(4) and U(4) are complete. Quantum gravity is unsolved in physics. General distributed consensus is unsolved in engineering. Same structural reason.

---

## 6. Control Theory Isomorphism

**[DERIVED]** The I/CC/U/SU loop is a closed-loop control system:

```
       ┌─────────────────────────────┐
       │                             │
  I(N) ──→ CC(N) ──→ U(N) ──→ SU(N) ─┘
 setpoint  error    control    plant
           signal   input      output
                                 │
                                 └──→ I(N+1) = new setpoint
```

**CC(N) = XOR(I(N), SU(N))** — the error signal is the logical difference between setpoint and output.

Two feedback paths:
- **INNER:** CC(N) refines I(N) at same level → successive approximation (precision)
- **OUTER:** SU(N) → I(N+1) → level promotion (new dimension)

This is also:
- **CPU cycle:** FETCH(I) → DECODE(CC) → EXECUTE(U→SU) → WRITEBACK(→I(N+1))
- **Full adder:** SUM = XOR (CC), CARRY = AND (overflow → next level)
- **Peano succession:** 0 exists (I(0)), every N has successor S(N) (SU(N)→I(N+1))

### Control Hierarchy by Level

| Level | Controller type | IPv8 analog |
|-------|----------------|-------------|
| I(0) | ON/OFF (bang-bang) | SUBSTRATE: link up/down |
| I(1) | Proportional (P) | LINK: frame valid/invalid |
| I(2) | PD (proportional-derivative) | COMMON-NET: route freshness |
| I(3) | PID (full classical) | TRANSPORT-8: seq tracking + RTT |
| I(4) | Adaptive | APPLICATION: capability negotiation |

---

## 7. Mapping to IPv8 OSI-ng Layers

**[TESTABLE]** Each IPv8 layer maps to the I/CC/U/SU quad:

| IPv8 Layer | I(N) invariant/test | CC(N) contract | U(N) interface | SU(N) implementation |
|-----------|--------------------|--------------|--------------|--------------------|
| **SUBSTRATE** | SubstratePort trait | Transport negotiation | send_frame/recv_frame | WS/UART/ICMP/UDP impls |
| **LINK (L0-2)** | 16-byte header format | EtherType + QAM I/Q/Phase (**4 bytes**) | MAC X:Y:Z addressing | Frame encap/decap |
| **COMMON-NET (L3)** | 128-bit address format | ARP-8 (maps L3↔L2) | IPv8 packet header (40B) | Forwarding table lookup |
| **TRANSPORT-8 (L4)** | Port allocation + protocol IDs | Checksum + sequence + flags | UDP-8/TCP-8/SOUL-8 headers | Connection state machines |
| **APPLICATION (L5-7)** | Session ID derivation | Capability negotiation | GodChat/DORA-8/SCE | Running application logic |
| **AI (L8-9)** | Model identity | Inference protocol | LLM→Agent interface | Agent execution |
| **PA (L10-11→L-1)** | τ invariant | The full loop back to L0 | Agency interface | PAI itself |

**Key discovery:** CC at LINK layer = exactly 4 bytes (EtherType + QAM I + QAM Q + Phase). The 4-byte CC overhead was designed into the protocol before the theory explained why it's always 4.

---

## 8. The Overflow Rule

**[DERIVED]** The generator space is cyclic with two's-complement overflow.

```
SU(2):  3 of  7 slots used  → room to grow
SU(3):  8 of  7 slots       → OVERFLOW, wraps to primitive
SU(4): 15 of 15 slots       → SATURATED, maximum density
SU(5): 24 of 31 slots       → room again (new bit-width)
```

Engineering protocol:
```
IF component.generators > 2^N - 1:
    OVERFLOW → decompose back to primitives
    OR → promote to N+1 bit-width (new abstraction layer)
```

IPv8 has 7 OSI-ng architectural layers but 12 numbered layers (L0-L11 wrapping to L-1). The overflow IS the wrap. L11→L-1 is the carry bit propagating back to the start.

---

## 9. Directions as Calculus

**[DERIVED]** The ^ and v operators are derivation and integration:

```
^ (forward)  = d/dx  = derivation   = entropy increasing = lose info
v (reverse)  = ∫dx   = integration  = entropy decreasing = accumulate (need +C)
```

**CC IS the +C** — the constant of integration. Without CC, the integral SU(N)→I(N+1) is ambiguous (infinite solutions). CC pins it to exactly one answer.

```
∫ SU(N) dN = I(N+1) + CC(N)
```

The fundamental theorem of calculus:
- ^(v(A)) = A (derive the integral → exact recovery)
- v(^(A)) = A + C (integrate the derivative → original PLUS lost information)

Not symmetric. That's why time has a direction.

---

## 10. Falsifiable Claims (Continuing from DPT v0.1)

| # | Claim | Type | Status |
|---|-------|------|--------|
| 7 | I(N) hierarchy is forced by generator count: I(1)=property, I(2)=behavior, I(3)=identity | DERIVED | DRAFT |
| 8 | I(0) = PRIMITIVE, axiomatic floor, unit circle is geometric form, τ is its invariant | AXIOM | DRAFT |
| 9 | Generator space is cyclic with two's-complement overflow; SU(3)→I(0) wrap | DERIVED | DRAFT |
| 10 | Level 4 triple: I(4)→TIME, U(4)→GRAVITY, SU(4)→ENTROPY | TESTABLE | DRAFT |
| 11 | c = 45° phase invariant, not velocity; CC = \|causality\| = c² | TESTABLE | DRAFT |
| 12 | Every level N has 4-part I/CC/U/SU structure; CC generates need for I(N+1) | AXIOM | DRAFT |
| 13 | I/CC/U/SU is cascade control system; τ = time constant, det(rotation)=1 | DERIVED | DRAFT |
| 14 | CC(N) = XOR(I(N), SU(N)); isomorphic to fetch-decode-execute-writeback | DERIVED | DRAFT |
| 15 | Loop is full adder; hierarchy is ripple-carry counter; Peano succession | DERIVED | DRAFT |
| 16 | ^ = derivation, v = integration; CC = constant of integration (+C) | DERIVED | DRAFT |

---

## 11. Vowel Structure (I-Centered Phonetics)

**[DERIVED]** The vowels are not linear (AEIOU). They spiral from I:

```
Standard:  A  E  I  O  U   (flat projection, alphabetical, wrong)
Centered:  I → A → E → O   with U as the closer/escape

I = identity (center, 0)
A = deepest integration from I (-8, most open, most primitive)
E = mid-integration (-4)
O = forward derivation (+6, rounded)
U = the closer — comes BEFORE, not after. The escape route back to consonants.
```

This reduces to 4 vowels + 1 escape (IAEO + U), mapping to 4 CC phases + the return:

| Vowel | CC Phase | Role |
|-------|----------|------|
| I | center (identity) | The reference — where all loops start and end |
| A | 1 (forward) | Most open, most primitive, assertive |
| E | i (superposed) | Mid-state, transitional |
| O | -1 (reversed) | Rounded, closed, reflective |
| U | -i (escape) | The closer — exit back to consonant space |

4 vowels + 4 anti-vowels should describe most phonetic structure, just as 4 DNA bases (A, T, G, C) describe most genetic structure. IaeoI is a valid loop. UaeIo is a valid escape sequence.

---

*This document maps a v0.1 theory to a v0.1 protocol. Both are falsifiable drafts. The mapping is structural, not metaphorical — but it requires formal proof to move beyond "consistent" to "necessary."*
