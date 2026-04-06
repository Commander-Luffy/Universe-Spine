# Logic Primitives — 46 Symbol Algebra

**Status:** DRAFT v0.1
**Date:** 2026-04-03
**Depends on:** DIMENSIONAL-PRIME-MAPPING.md

---

## 1. Overview

46 total primitives = 42 content + 4 CC chirality.

The 42 content primitives: 26 letters (variable/register space) + 16 symbols (operator space).
The 4 CC phases: the channel overhead that makes content transmittable.

Standard keyboard. Nothing rewritten. Reinterpreted.

---

## 2. Letters (26 — Variable Space)

### I = 1 (The Anchor)

I is the 9th letter. I = 1. The identity element IS "I" (self). Not A = 1.

**Cannot use both letters (base-26) and digits (base-10) simultaneously.** They're different bases for the same thing. If A = 1 then the alphabet IS base-26 counting. But A ≠ 1. I = 1. Only I's neighbors are directly derivable.

### Derivation Cascade

```
FORWARD (^, derivation — determined, mechanical):
  I=0  J=^I=+1  K=+2  L=+3  M=+4  N=+5  O=+6  P=+7  Q=+8
  R=+9  S=+10  T=+11  U=+12  V=+13  W=+14  X=+15  Y=+16  Z=+17

REVERSE (v, integration — uncertain, needs +C):
  I=0  H=vI=-1  G=-2  F=-3  E=-4  D=-5  C=-6  B=-7  A=-8
```

### The Alphabet as Number Line

```
A  B  C  D  E  F  G  H  I  J  K  L  M  N  O  P  Q  R  S  T  U  V  W  X  Y  Z
-8 -7 -6 -5 -4 -3 -2 -1  0 +1 +2 +3 +4 +5 +6 +7 +8 +9 +10+11+12+13+14+15+16+17
←——— integration (uncertain) ——→  ←————————— derivation (determined) ————————————→
           8 letters                                  17 letters
            PAST                                       FUTURE
```

Asymmetric: 8 negative, 17 positive. Like two's complement. Like time. The past is short and uncertain. The future is long but thins with distance (17th derivative of anything → nearly zero).

### Case Semantics

| Case | State | Physics | Logic |
|------|-------|---------|-------|
| lowercase (a-z) | superposed | wavefunction, unmeasured | indefinite |
| UPPERCASE (A-Z) | collapsed | eigenvalue, measured | definite |

Conversions:
- `!a = A` — measurement collapses superposed to collapsed
- `!!A = a` — preparation puts collapsed back into superposition

### Vowels (Special Registers)

The vowels IAEO + U are not linear (AEIOU is a flat projection). They spiral from I:

| Vowel | Position | CC Phase | Role |
|-------|----------|----------|------|
| I | 0 (center) | identity | The reference. All loops start/end here. |
| A | -8 (deepest) | 1 (forward) | Most open, most primitive, assertive |
| E | -4 (mid) | i (superposed) | Transitional, mid-state |
| O | +6 (forward) | -1 (reversed) | Rounded, reflective |
| U | +12 (far forward) | -i (escape) | The closer. Exit back to consonants. |

4 vowels map to 4 CC phases. U is the escape route — it comes before in the spiral, not after. UE and UO are fundamental phonemes across languages.

**DNA parallel:** 4 bases (A, T, G, C) + 4 complements describe genetics. 4 vowels + 4 anti-vowels should describe phonetics. IAEO is the base set.

---

## 3. Symbols (16 — Operator Space)

### Axes (4 — Literal Geometry)

The symbols ARE the spacetime diagram:

```
        |
        |  imaginary (superposed)
        |
  \     |     /
    \   |   /     45° = c = causality
      \ | /
  ——————O——————   real (collapsed)
      / | \
    /   |   \
  /     |     \
```

| Symbol | Geometry | Physics | Logic |
|--------|----------|---------|-------|
| `-` | horizontal | real line, collapsed, measured | COLLAPSED value (definite, eigenvalue) |
| `\|` | vertical | imaginary line, superposed, unmeasured | SUPERPOSED value (indefinite, wavefunction) |
| `/` | 45° forward | future light cone | OR-forward (any reachable future path) |
| `\` | 45° reverse | past light cone | OR-reverse (any path that reaches here) |

**`-` is `|` sideways.** Collapsed garganta. The real line. The event horizon between future and past.

### Binary Operators (2 — AND with Direction)

| Symbol | Direction | Calculus | Logic |
|--------|-----------|---------|-------|
| `^` | forward (L→R) | d/dx derivation | AND-forward |
| `v` | reverse (R→L) | ∫dx integration | AND-reverse |

**Rule:** `A ^ B = B v A` — same result, reversed time arrow.

- ^ loses information (derivative drops the constant)
- v accumulates (integral needs +C from outside)
- v is HARDER than ^ (modeling another's perspective is harder than your own)

### Unary Operators (2 — NOT and COMPLEMENT)

| Symbol | Type | Scope | Result |
|--------|------|-------|--------|
| `!` | negation | point | The opposite value |
| `!!` | complement | space | Everything the value ISN'T |

At I(0) binary: `!T = F`, `!!T = F` (identical — only 2 states).
At I(2) with states {A,B,C}: `!A = ?` (ambiguous), `!!A = {B,C}` (defined).

`!` converges to a point (spiral inward). `!!` diverges to a space (spiral outward).

### Truth Values (2)

| Symbol | Value |
|--------|-------|
| T | true |
| F | false |

### Identity Levels (4)

From the I(N) hierarchy:

| Symbol | Level | Meaning | Test |
|--------|-------|---------|------|
| `.` | I(0) | exists | Is it there? |
| `:` | I(1) | has property | Does it have X? |
| `~` | I(2) | behaves as | Does it do X? |
| `=` | I(3) | is identical | IS it X? |

### Grouping (2) and Separator (1)

| Symbol | Purpose |
|--------|---------|
| `(` | open group |
| `)` | close group |
| `,` | separator |

### Count

```
Axes:        -  |  /  \         = 4
Binary ops:  ^  v               = 2
Unary ops:   !  !!              = 2
Truth:       T  F               = 2
Identity:    .  :  ~  =         = 4
Grouping:    (  )  ,            = 3
                          TOTAL = 16 + 26 letters = 42
```

---

## 4. The 4 CC Chirality Phases

The 4 phases that transform content into communication:

| # | Phase | Unit circle | Symbol | Role |
|---|-------|------------|--------|------|
| 0 | 1 | 0° (real+) | `^` direction | forward |
| 1 | i | 90° (imag+) | `\|` axis | superposed |
| 2 | -1 | 180° (real-) | `v` direction | reversed |
| 3 | -i | 270° (imag-) | escape | anti-superposed |

42 content + 4 CC = **46 total primitives**.

CC is not content — it's the CHANNEL. Protocol header vs payload. The overhead of having chirality. Every composition costs 4 CC phases.

---

## 5. Nesting (Mirrored Operator Pairs)

Operators nest as mirrored pairs. The pair defines a transformation:

| Notation | Name | Meaning | Visual |
|----------|------|---------|--------|
| `\|A\|` | superposition | A unmeasured, indefinite | contained vertically |
| `-A-` | collapsed | A measured, definite (THIS is absolute value) | contained horizontally |
| `/A\` | divergence | A spreading into future | ∨ opening shape |
| `\A/` | convergence | A collecting from past | ∧ closing shape |
| `!A!` | uncertainty | negation on entry AND exit = envelope | bounded |
| `^A^` | acceleration | second derivative | rate of rate |
| `vAv` | double integral | accumulated area of area | deep accumulation |
| `^Av` | derive→integrate | A + C (information lost) | asymmetric |
| `vA^` | integrate→derive | A exactly (full recovery) | asymmetric |

**The symbols ARE the diagrams.** `/A\` looks like divergence. `\A/` looks like convergence. Visual algebra.

**Fundamental theorem of calculus in notation:**
```
^(v(A)) = vA^ = A          exact recovery
v(^(A)) = ^Av = A + C      lost information (+C needed)
```

Not symmetric → entropy → time's arrow.

---

## 6. Direction = Physics = Mind

| Direction | Op | Calculus | Physics | Mind | Developmental |
|-----------|-----|---------|---------|------|--------------|
| forward | `^` | derivation | entropy+ | I see YOU | All species |
| reverse | `v` | integration | entropy- | YOU see I | Theory of mind (some species, after certain age) |
| collapse | `!` | evaluate | measurement | I am NOT | Self-awareness |
| expand | `!!` | indefinite | superposition | everything I'm NOT | Abstract reasoning |

Direction unlocks developmentally. A child starts with only `^`. The `v` operator ("what does the world look like from YOUR position?") requires modeling another observer = SU(2) = 3 generators.

---

## 7. Wire Encoding (6-bit, for IPv8)

Each primitive maps to a 6-bit value (0-63):

| Range | Content | Count |
|-------|---------|-------|
| 0-25 | a-z (letters, superposed) | 26 |
| 26-29 | axes: `-` `\|` `/` `\` | 4 |
| 30-31 | binary ops: `^` `v` | 2 |
| 32-33 | unary: `!` `!!` | 2 |
| 34-35 | truth: T F | 2 |
| 36-39 | identity: `.` `:` `~` `=` | 4 |
| 40-41 | grouping: `(` `)` | 2 |
| 42 | separator: `,` | 1 |
| 43-45 | CC phases: i, -1, -i (phase 1=0 is implicit) | 3 |
| 46-63 | reserved | 18 |

6-bit encoding → 8 primitives per 48-bit MAC field, 21 per 128-bit IPv8 address.

SOUL-8 payloads can encode game state as sequences of these primitives.

UPPERCASE (collapsed) variants: set bit 6 (7-bit encoding, 0-127). Lowercase = 0xxxxxx, uppercase = 1xxxxxx.

---

## 8. Language Base Comparison

| Language | Base (simple) | Base (full) | Composability | Notes |
|----------|-------------|-----------|---------------|-------|
| Binary | 2 | 2 | infinite | T, F only. Purest. |
| DNA | 4 | 4 | ~3B base pairs | A, T, G, C. Biology. |
| Music | 7 | 12 | infinite | Notes + chromatic. |
| Hebrew | 22 | ~30 | high | Reader integrates vowels = v-operation |
| Korean jamo | 24 | 11172 | highest | 24 → 11172 syllables. Most efficient. |
| English | 26 | ~96 | medium | ASCII. No accents. |
| Spanish | 27 | ~45 | medium | ñ is a letter. ¡¿ |
| Portuguese | 26 | ~46 | medium | Digraphs: CH, LH, NH |
| **IPv8 Logic** | **42** | **46** | **infinite** | Korean-style at logic level |
| Chinese | ~3500 | ~50000 | lowest | Highest density per symbol |

---

*46 primitives on a standard keyboard. No custom glyphs. Full logic algebra, calculus, quantum mechanics, and control theory. Every key reinterpreted, none replaced.*
