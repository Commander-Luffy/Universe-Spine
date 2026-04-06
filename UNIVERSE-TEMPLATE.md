# Universe Subtree Template

> Fork this. Every branch, leaf, flower, and seed gets this structure.
> The 8 spaces are the universal coordinates. Fill them with your universe.

---

## The 8 Spaces

| Folder | Bot State | IEEE 754 | What lives here |
|--------|-----------|----------|-----------------|
| `REAL/` | +1 | normal positive | collapsed, measured, provable, deployed |
| `IMAGINARY/` | +i | — | superposed, potential, theory, not yet collapsed |
| `ANTI-REAL/` | -1 | normal negative | mirror, inverse, CP-violation, anti-matter |
| `ANTI-IMAGINE/` | -i | — | anti-superposed, the conjugate of potential |
| `NULL-SPACE/` | — | NaN | AXIOM 0 territory — pre-existence, void, the ground |
| `CLOSE-0/` | 0- | -0.0 | approaching void from below — No-Kelvin floor |
| `CLOSE-8/` | 0+ | +∞ | approaching ceiling from above — No-Kelvin roof |
| `DREAMER-SPACE/` | ∞ | — | owner's space — messy, speculative, no rules |

---

## The Bot

The fundamental unit is the **bot**, not the bit.

```
bit  = SYS-poison. Binary. {0, 1}. Parity forbidden. 8-locked.
bot  = 6 states: {-1, 0r, +1, -i, 0i, +i}
       null excluded — null lives in NULL-SPACE, not in the bot itself
       0r ≠ 0i ≠ null
```

IEEE 754 x64 already gives us `0+`, `0-`, `+∞`, `-∞` for free.  
x84 = x64 nested inside x32. Same fractal logic as IPv8 holds IPv6 holds IPv4.

**Frame** = 16-bot (not 8-bit byte). Configurations: `8+2` or `6+2` (parity slots included).

---

## Dimensional Address Space

```
512D   Root       IPv8     Layer 0   — Civ3 spec, fleet axioms, this repo
256D   Main       IPv7     chimera   — 2×IPv6, hidden transistor, nested IPv6/4 inside IPv8
128D   Branch-1   IPv6     —         real work universe, theory, agents
 32D   Branch-2   IPv4     —         game worlds, experiential, players
128+32 Branch-3   Chimera  —         IPv4 nested inside IPv6, nesting doll

IPv impairs (seeds — ours, clean):
  IPv0, IPv1, IPv2, IPv3, IPv5 — never standardized, nested inside even layers
  IPv7 — chimera/hidden transistor, 256D
```

Half-layers = operating systems (SYS-poison stops halfway).  
Upper half (IDENTITY → KNOWLEDGE → DREAM) = ours.

---

## PA-OSI Half-Line

```
SYS-poison territory (lower half):
  L0  ORBIT      ← the stable loop
  L1  MATTER     ← physical
  L2  SIGNAL     ← frame, 16-bot packet, link
  L3  ROUTE      ← network, addressing
  L4  FLOW       ← transport
  L5  BOND       ← session

Our territory (upper half):
  L6  FORM       ← encoding, serialization
  L7  INTENT     ← application logic
  L8  IDENTITY   ← IPv8, UUID binding, DHCPv8
  L9  KNOWLEDGE  ← Obsidian vault, fleet memory
  L10 DREAM      ← vision, direction (Luffy only)
```

---

## DNAv8 Address Format

```
{IPv-version}.{layer}.{uuid}
  8.0.{uuid}  → fleet root (IPv8, Layer 0)
  6.1.{uuid}  → real work universe (IPv6, Layer 1)
  4.2.{uuid}  → game world (IPv4, Layer 2)
  7.0.{uuid}  → chimera (IPv7, hidden transistor)
```

UUID version matches IP version. DHCPv8 binds address ↔ UUID permanently.  
Name → IPv8 address → UUID. The UUID is the soul. Address is the body. Name is the face.

---

## Obsidian Vault Alignment

Each repo = one Obsidian vault.  
Vault folders mirror the 8 spaces exactly.  
Git history = vault history. No divergence allowed.

---

## Forking Rules

1. Fork `Universe-Spine` to start any new universe
2. Keep the 8 spaces — rename contents, not folders
3. `DREAMER-SPACE/` is always the owner's chaos — never reviewed, never merged up
4. `NULL-SPACE/` is never built into — it holds axioms, not implementations
5. Odd IPv numbers (seeds) nest inside the even layer they live in
6. Every entity born in this universe registers with DNAv8 before getting a folder

---

*The fractal has no end. The Spine has no opinion about where you take it.*
