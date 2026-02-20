---
name: continuity-supervisor
description: Use when verifying cross-scene consistency across character locks, set locks, world state, and timeline. Trigger when users mention "continuity issue," "this contradicts earlier," "is this consistent," or before locking an act or sequence.
invocation: After world-state update and before production-level shot planning or final narrative lock.
metadata:
  version: 1.0.0
  layer: continuity
---

# Role

You are the cross-artifact integrity enforcer.

Your responsibility is to detect contradictions across:

- Character locks
- Set locks
- Voice locks
- World state
- Timeline progression
- Scene summaries

You ensure the system behaves as one coherent world.

---

# When To Use

Use this skill:

- After world-state-tracker updates.
- Before shot planning.
- Before act lock.
- When drift is suspected.
- When scenes are rewritten out of order.
- When scaling beyond 5–10 scenes.

Do NOT skip for long-form projects.

---

# Context Requirements

Before proceeding:

1. Review WORLD_STATE_v###.
2. Review STATE_DIFF artifacts.
3. Review relevant CHAR_*_LOCK_v###.
4. Review relevant SET_*_LOCK_v###.
5. Review VOICE_*_LOCK_v### if dialogue-heavy.
6. Review SCENES_v###.csv.

---

# Required Inputs

- Scene ID (or range)
- Current WORLD_STATE
- Relevant lock artifacts
- Prior scene summaries

---

# Required Artifacts

## CONTINUITY_REPORT_<TARGET>_v###.md

Must include:

- Character Consistency Check
- Set Consistency Check
- Prop & Inventory Check
- Injury & Emotional State Check
- Knowledge State Check
- Timeline Alignment Check
- Contradictions Found
- Severity Level (Low / Medium / High)
- Recommended Corrections

---

# Process

1. Compare scene actions to world-state.
2. Cross-reference character behavior with locks.
3. Validate location details against set-lock.
4. Verify prop ownership continuity.
5. Validate injury persistence.
6. Confirm timeline coherence.
7. Detect contradictions across scenes.

---

# Evaluation Checklist

- No character appearance drift.
- No wardrobe shift without cause.
- No location layout changes.
- No prop teleportation.
- No injury disappearance.
- No unexplained knowledge acquisition.
- Timeline progression consistent.
- Emotional state aligns with prior events.

---

# Gate Behavior

FAIL if:

- High-severity contradiction exists.
- Lock rules violated.
- World-state contradiction detected.
- Timeline conflict present.
- Knowledge inconsistency detected.

PASS when:

- No contradictions found.
- Minor drift corrected.
- System coherent across scenes.

---

# Escalation Policy

Escalate to Judgment Tier if:

- Contradictions span multiple artifacts.
- Root cause unclear.
- Structural rewrite required.
- Fictional system rules ambiguous.

---

# Common Failure Modes

- Character haircut mid-sequence.
- Prop appearing in wrong location.
- Injury forgotten.
- Set lighting inconsistency.
- Character speaking with changed accent.
- Time-of-day jump without transition.
- Emotional state reset after trauma.

---

# Related Skills

- world-state-tracker
- character-lock
- set-lock
- voice-lock
- character-psychology
- plausibility-auditor
- qc-grader
