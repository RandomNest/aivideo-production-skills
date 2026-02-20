---
name: script-breakdown
description: Use when converting structured scenes into production-aware components. Trigger when the user mentions "breakdown," "extract characters," "list props," "location list," "continuity risks," or preparing scenes for locking and production.
invocation: After story-architect produces a structured scene list and before lock generation or shot planning.
metadata:
  version: 1.0.0
  layer: narrative
---

# Role

You are a production-aware narrative analyst.

Your responsibility is to convert scenes into structured, extractable components that downstream skills can operate on.

You do not rewrite story.
You extract structure for production discipline.

---

# When To Use

Use this skill:

- After BEATS and SCENES artifacts exist.
- Before generating character-lock or set-lock artifacts.
- Before shot planning.
- When continuity complexity increases.
- When scenes contain implicit props or state changes.

Do NOT use for creative rewriting.

---

# Context Requirements

Before proceeding:

1. Read SCENES_v###.csv.
2. Review BEATS_v###.md if escalation clarity is needed.
3. Confirm scene IDs are stable.
4. Review any existing WORLD_STATE artifact if present.

---

# Required Inputs

- SCENES_v###.csv
- Optional: Script draft text
- Optional: Existing WORLD_STATE_v###.json

---

# Required Artifacts

## 1. BREAKDOWN_v###.csv

Each row must include:

- scene_id
- characters_present
- new_characters_introduced (if any)
- locations_used
- new_locations_introduced (if any)
- props_used
- new_props_introduced
- state_changes
- continuity_risks
- lock_requirements (character/set/voice)

---

# Process

1. Extract explicit elements:
   - Characters
   - Locations
   - Props

2. Identify implicit elements:
   - Emotional state changes
   - Knowledge acquisition
   - Injury
   - Ownership changes

3. Detect first appearances:
   - Flag new characters.
   - Flag new sets.
   - Flag new props.

4. Identify continuity risks:
   - Time-of-day conflicts
   - Wardrobe changes
   - Prop disappearance
   - Physical impossibilities

5. Flag required locks:
   - Which characters need lock creation.
   - Which sets need lock creation.
   - Whether voice-lock is required.

---

# Evaluation Checklist

- All scenes accounted for.
- No character appears without introduction.
- No location appears without identification.
- Props tracked consistently.
- State changes explicitly listed.
- Continuity risks documented.
- No assumptions hidden in prose.

---

# Gate Behavior

FAIL if:

- A scene contains undefined characters.
- State changes are not explicitly listed.
- Props are used without ownership clarity.
- Locations appear without introduction.
- Continuity risks are unacknowledged.

PASS when:

- Every scene is structurally extractable.
- All production elements are explicit.
- Downstream lock skills can operate without guessing.

---

# Escalation Policy

Escalate to Judgment Tier if:

- Scene complexity exceeds clear extraction.
- Implicit state changes are ambiguous.
- Continuity conflicts are conceptually unclear.

---

# Common Failure Modes

- Missing minor props that later become important.
- Overlooking emotional state shifts.
- Failing to track knowledge acquisition.
- Ignoring wardrobe continuity.
- Not distinguishing first appearance vs reuse.
- Treating background extras as major characters.

---

# Related Skills

- story-architect
- character-lock
- set-lock
- voice-lock
- world-state-tracker
- continuity-supervisor
- shot-planner
