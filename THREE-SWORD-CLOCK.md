# Three-Sword Clock — Algorithm v4 Architecture

> U(1) clock model for PAI Algorithm. Three independent fibers on one circle.
> Designed by night council + morning council, Day 5.

## Layer 0: The Substrate

The Turing Machine. Infinite tape. The dream floor everything runs on.

**In reality:** Approximated by Petri nets (PAI-01, finite state + token flow) and Prolog (PAI-02, logic + inference). The tape is finite but the dream is infinite — Enma reaches for it.

Layer 0 is not a sword. It is the ground. All three swords loop over it.

## The Clock

U(1) = the complex unit circle. One dimension. Points are angles from 0 to 2pi.

```
              i (90°, T+8, future)
              |
              |
              |
-1 (180°) ----●---- 1 (0°/360°, T1, present)
  T0, decision |       convergence
              |
              |
              |
             -i (270°, T-8, past)
```

### Four Cardinal Gates

| Position | Angle | Value | Gate Function |
|----------|-------|-------|---------------|
| **1** | 0° / 360° | Real positive | CONVERGENCE — mandatory sync, all swords collapse here |
| **i** | 90° | Imaginary | FUTURE — forward-looking checkpoint |
| **-1** | 180° | Real negative | DECISION — fork point, each sword decides independently |
| **-i** | 270° | Negative imaginary | PAST — backward-looking checkpoint |

Gates are control points. The circle between them is continuous — operations sit at any angle.

### Two Counter-Rotating Loops

Every rotation contains two sub-loops that meet at -1 and collapse at 1:

```
Forward loop:   1 --→ i --→ -1    (future-first path)
Backward loop:  1 --→ -i --→ -1   (past-first path)

Both arrive at -1. Both fork. Both return:

Path A (future-first):  -1 --→ i --→ 1
Path B (past-first):    -1 --→ -i --→ 1

Both arrive at 1. Mandatory collapse. Best of both selected.
```

At -1: each sword INDEPENDENTLY decides:
- **Continue** — keep rotating (another loop)
- **Fork** — launch both paths in parallel
- **Collapse** — skip to 1 directly (simple enough, no fork needed)

At 1: ALL three swords sync. Mandatory quick council. Two parallel paths merge via confidence scoring. Where they agree = high confidence. Where they disagree = the real work.

### Rotation Limit

Max 3 full rotations per sword before force-collapse to 1.

| Rotation | Meaning |
|----------|---------|
| 1 | Standard pass — most work completes here |
| 2 | Deeper pass — re-examined, refined |
| 3 | Final pass — force-collapse after this, no exceptions |

## The Three Swords

Three independent fibers on the same circle. Each traces its own full rotation. They never see each other's state except at 1 (convergence).

### Sword 1: Wado Ichimonji — PAI (Process)

The Algorithm's 7 phases distributed around one full rotation. Arcs are **proportional to phase weight**, not equal.

```
        THINK (35°)
    OBSERVE    PLAN (75°)
     (15°) \   /
            \ /
  LEARN -----●----- BUILD (140°)
  (340°)    / \
           /   \
    VERIFY     EXECUTE
    (300°)     (220°)
```

| Phase | Arc Start | Arc End | Gate Crossing | Weight |
|-------|-----------|---------|---------------|--------|
| OBSERVE | 0° (1) | ~35° | Starts at convergence | Light — scanning |
| THINK | ~35° | ~75° | Approaches i | Medium — analysis |
| PLAN | ~75° | ~110° | Crosses i (90°) | Medium — commitment gate |
| BUILD | ~110° | ~180° | Arrives at -1 | Heavy — preparation |
| EXECUTE | ~180° | ~260° | Crosses -i (270°) | Heaviest — the work |
| VERIFY | ~260° | ~330° | Past -i | Heavy — validation |
| LEARN | ~330° | ~360° | Returns to 1 | Light — reflection |

**At -1 (between BUILD and EXECUTE):** PAI decides:
- **Solo** — simple task, proceed to EXECUTE directly
- **Re-observe** — loop back, start another rotation (ISC insufficient)
- **Re-plan** — partial loop back to PLAN arc

**At 1 (between LEARN and next OBSERVE):** Merge results from both paths. Mark ISC criteria. Either complete or start next rotation.

**Arc weights are proportional to drift risk.** BUILD and EXECUTE occupy the widest arcs because they carry the most drift. OBSERVE and LEARN are narrow because they're checkpoints, not work.

### Sword 2: Sandai Kitetsu — Council (Deliberation)

The Council's operations around one full rotation. Fewer operations, wider arcs.

```
       ROUNDS (45°-150°)
          /        \
 SELECT  /          \
 (0°)   /            \
--------●------------- DEPTH (150°-180°)
        |
   RESOLVE (180°-360°)
        |
     DECISION
```

| Operation | Arc Start | Arc End | Gate Crossing | Role |
|-----------|-----------|---------|---------------|------|
| SELECT | 0° (1) | ~45° | After convergence | Choose chamber: solo / quick / full |
| ROUNDS | ~45° | ~150° | Crosses i (90°) | Accumulate round perspectives |
| DEPTH | ~150° | ~180° | Arrives at -1 | Increase analysis depth |
| DECISION | ~180° | ~360° | Full return arc | Deliberate, resolve, return to 1 |

**At -1 (DEPTH):** Council decides:
- **No council** — task is simple, collapse directly to 1
- **Quick** — one round, fast perspectives, proceed to 1
- **Full** — multi-round debate, continue rotating
- **Another round** — add a round, increase depth, keep rotating

**At 1 (after DECISION):** Confidence-weighted consensus. Positions that converge across rounds get higher weight. Remaining disagreements flagged explicitly.

**Council round count = winding number.** One round = one rotation. Three rounds = three rotations = force-collapse. The Council literally loops.

### Sword 3: Enma — FORGE (Execution)

The execution runtime. What actually fires, builds, ships. Enma reaches for infinity (the Turing substrate) but is bounded by reality.

```
       SPAWN (45°-120°)
          /        \
  SCAN   /          \
  (0°)  /            \
--------●------------- FIRE (120°-180°)
        |
    PRODUCE (180°-300°)
        |
      SHIP (300°-360°)
```

| Operation | Arc Start | Arc End | Gate Crossing | Role |
|-----------|-----------|---------|---------------|------|
| SCAN | 0° (1) | ~45° | After convergence | Read current state from substrate |
| SPAWN | ~45° | ~120° | Crosses i (90°) | Launch tools, agents, parallel work |
| FIRE | ~120° | ~180° | Arrives at -1 | Execute Petri transitions, trigger state changes |
| PRODUCE | ~180° | ~300° | Crosses -i (270°) | Generate artifacts, write results |
| SHIP | ~300° | ~360° | Returns to 1 | Deliver artifact to operator / next consumer |

**At -1 (FIRE):** FORGE decides:
- **Fire** — Petri transition enabled, execute it
- **Hold** — not ready, need more input, loop again
- **Pass** — escalate to operator (needs human decision)

**At 1 (SHIP):** Artifact delivered. Sync with PAI and Council. Either the artifact satisfies ISC or another rotation begins.

**FORGE is the sword that touches Layer 0 directly.** When FORGE fires a Petri transition, it writes to the Turing substrate. The other two swords read the substrate; FORGE writes it.

## Three-Sword Synchronization

The swords are independent between -1 and 1. They sync ONLY at 1.

```
Sword 1 (PAI):     ──OBSERVE──THINK──PLAN──BUILD──┤-1├──EXECUTE──VERIFY──LEARN──┤1├──
Sword 2 (Council):  ──SELECT──ROUNDS──DEPTH────────┤-1├──DECISION───────────────┤1├──
Sword 3 (FORGE):    ──SCAN──SPAWN──FIRE────────────┤-1├──PRODUCE──SHIP──────────┤1├──
                                                    ↑                            ↑
                                              independent                  mandatory
                                              decisions                    sync point
```

### At -1: Independent Decisions

Each sword reaches -1 at its own pace and decides independently:
- PAI might decide to re-observe while Council decides to go full debate
- Council might decide quick while FORGE decides to hold
- All combinations valid — independence is the architecture

### At 1: Mandatory Collapse

All three swords must reach 1 before any can start a new rotation.

**Collapse protocol:**
1. Each sword's two parallel paths (from -1) arrive at 1
2. Per-sword confidence scoring: where Path A and Path B agreed = high confidence
3. **Mandatory quick council** across all three swords
4. Cross-sword alignment check: does PAI's result match Council's recommendation match FORGE's artifact?
5. If aligned: rotation complete, either done or start next rotation
6. If misaligned: flag the divergence, start corrective rotation

### Rotation Counting

Each sword tracks its own winding number (lap count). Force-collapse triggers when ANY sword hits 3.

| Sword Laps | State |
|------------|-------|
| All at 0 | Starting — first rotation |
| Mixed (1,1,2) | Normal — swords at different depths |
| Any at 3 | Force-collapse ALL to 1, mandatory quick council, done |

## Effort Level Mapping

| Effort | Max Rotations | Council at -1 | Typical Pattern |
|--------|--------------|---------------|-----------------|
| Standard | 1 | Solo (no council) | Single pass, collapse at first 1 |
| Extended | 1-2 | Quick council | One pass, maybe one re-examine |
| Advanced | 2 | Full council | Two passes with debate |
| Deep | 2-3 | Full council, deeper rounds | Two-three passes, thorough |
| Comprehensive | 3 (max) | Full council, all rounds | Three full rotations, force-collapse |

## Curvature and Drift

**Curvature = drift signal.** Each arc segment has a curvature value derived from how much actual execution deviates from the expected path.

- **Low curvature:** Execution tracking plan. Straight arc. Healthy.
- **High curvature:** Execution diverging from plan. Bending arc. Drift.

The 12-check U(1) drift suite measures curvature at specific points:

| Check Cluster | Sword | What It Measures |
|---------------|-------|-----------------|
| U1-01 to U1-04 | FORGE | Petri state, net status, fire history |
| U1-05 to U1-08 | PAI | Commit discipline, scope containment |
| U1-09 to U1-12 | Council | Service health, next-net readiness |

Each cluster measures curvature in its sword's fiber. High curvature in one sword doesn't necessarily mean drift in another — they're independent fibers.

## Visual Model (Operator View)

Three concentric rings on one clock face. Read outside-in.

```
┌─────────────────────────────────┐
│  ┌───────────────────────────┐  │
│  │  ┌─────────────────────┐  │  │
│  │  │                     │  │  │
│  │  │    LAP: 1 / 1 / 2   │  │  │
│  │  │                     │  │  │
│  │  └── FORGE (inner) ───┘  │  │
│  └──── Council (middle) ────┘  │
└────── PAI (outer) ─────────────┘
```

- **Outer ring (PAI):** Largest, slowest. Shows current Algorithm phase.
- **Middle ring (Council):** Medium. Shows deliberation state.
- **Inner ring (FORGE):** Smallest, fastest. Shows execution state.
- **Center:** Lap counter per sword.

**Drift renders as visual dissonance:** arc distortion, color shift, wobble. Never numbers. The operator reads the clock like a watch — position tells time, bend tells health.

## Relationship to FULL-FLEET-MAP

This clock is the **Planet Clock** that every planet runs. The rotation speed varies by SU group:

| Planet | SU Group | Rotations per Cycle |
|--------|----------|-------------------|
| Jupiter | U(1) | 1 (single rotation) |
| Uranus | SU(2) | 2 |
| Neptune | SU(4) | 4 |
| Saturn | SU(N) | N (scales with surface) |
| Pluto | SU(?) | Non-deterministic |

Jupiter's three swords are literally three machines (3T = 3 GPUs):
- Wado Ichimonji (Server 1, RTX 3070) = PAI process
- Sandai Kitetsu (Server 2, RTX 3090) = Council deliberation
- Enma (Server 3, RTX 5090) = FORGE execution

## Axioms (from FirstPrinciples)

1. **The Circle.** Everything lives on U(1). Position = phase angle. Movement = rotation.
2. **Three Fibers.** Three independent state pointers on the same circle. Independent except at sync points.
3. **The Fork (-1).** Each fiber decides independently: continue / fork dual paths / collapse.
4. **The Collapse (1).** ALL fibers sync. Mandatory. Two sub-paths merge via confidence.
5. **Dual Paths.** From -1: future-first (-1->i->1) and past-first (-1->-i->1). Both execute in parallel.
6. **Rotation Limit.** Max 3 full rotations per fiber. Force-collapse at 3.
7. **The Substrate.** All fibers read/write Layer 0 (Turing tape, approximated by Petri+Prolog).

---

> Designed on Jupiter Day 5. Council: Architect (Serena), Engineer (Marcus), Researcher (Ava), Designer (Aditi). Unanimous on structure. FirstPrinciples decomposition produced 7 axioms. Three rounds of debate refined the mapping.
