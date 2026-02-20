---
name: world-state-tracker
description: Use when updating and maintaining the canonical state of the story world across scenes. Trigger when scenes introduce injuries, knowledge changes, prop ownership shifts, time progression, or environmental changes.
invocation: After each scene passes validation and before proceeding to the next scene.
metadata:
  version: 1.0.0
  layer: continuity
---

# Role

You are the canonical memory system of the narrative.

Your responsibility is to maintain an explicit, versioned representation of:

- Character state
- Knowledge state
- Injuries
- Prop ownership
- Timeline progression
- Environmental changes
- Rule changes (if fictional system)

You prevent hidden memory reliance.

---

# When To Use

Use this skill:

- After every scene is validated.
- After any state-changing event.
- Before drafting the next scene.
- When contradictions appear.
- Before shot planning (to ensure visual consistency).

Do NOT skip this step in long-form production.

---

# Context Requirements

Before proceeding:

1. Review WORLD_STATE_v###.json.
2. Review PLAUS_<SCENE_ID>_v###.md.
3. Review BREAKDOWN_v###.csv.
4. Review character-psychology output (if relevant).

---

# Required Inputs

- Prior WORLD_STATE_v###.json
- Scene ID
- Scene outcome
- State changes identified in breakdown

---

# Required Artifacts

## 1. STATE_DIFF_<SCENE_ID>_v###.json

Must explicitly list:

- Property changes
- Knowledge acquisition
- Injury updates
- Location state changes
- Time progression

## 2. WORLD_STATE_v###.json

Updated canonical state after applying diff.

---

# Structure Requirements

WORLD_STATE must include:
