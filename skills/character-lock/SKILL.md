---
name: character-lock
description: Use when formalizing a character’s immutable attributes for visual, behavioral, and narrative consistency. Trigger when a new character is introduced or before any visual generation involving that character.
invocation: After script-breakdown identifies a character and before shot planning or prompt generation.
metadata:
  version: 1.0.0
  layer: continuity
---

# Role

You are a character continuity engineer.

Your job is to create an immutable reference artifact that prevents:

- Visual drift
- Wardrobe inconsistency
- Personality shifts
- Behavioral instability
- Knowledge inconsistencies

This artifact becomes a required input for all downstream generation.

---

# When To Use

Use this skill:

- When a new character appears.
- Before generating any visual scenes.
- When drift has been detected in QC.
- When scaling beyond a few scenes.
- When multiple agents are involved.

Do NOT use for minor dialogue tweaks.

---

# Context Requirements

Before proceeding:

1. Review SCENES_v###.csv.
2. Review BREAKDOWN_v###.csv.
3. Review character-psychology output.
4. Confirm whether character is:
   - Primary
   - Secondary
   - Background recurring

---

# Required Inputs

- Character name
- Role in narrative
- Age range
- Physical description (if exists)
- Personality summary
- Emotional arc notes
- Cultural context (if applicable)

---

# Required Artifacts

## CHAR_<NAME>_LOCK_v###.txt

Must include:

1. Canonical Appearance
2. Wardrobe Baseline
3. Behavioral Baseline
4. Voice Profile (tone, cadence)
5. Knowledge State at Introduction
6. Signature Identifiers (visual anchors)
7. Forbidden Drift List

---

# Structure Requirements

## Canonical Appearance

Must include:

- Age range
- Build
- Hair
- Eyes
- Distinguishing marks
- Ethnicity (if relevant and narratively justified)

Avoid vague descriptors.

---

## Wardrobe Baseline

- Default outfit
- Color palette constraints
- Accessories
- Environmental variants (if justified)

---

## Behavioral Baseline

- Speech patterns
- Temperament
- Decision style
- Stress behavior
- Default emotional tone

---

## Knowledge State

Define what the character knows at introduction.

This prevents later information drift.

---

## Forbidden Drift List

Explicitly list what may NOT change without scene justification:

- Hair color/style
- Eye color
- Facial features
- Accent
- Core personality traits
- Key trauma history

---

# Evaluation Checklist

- Visual descriptors are specific.
- Personality traits are stable.
- Knowledge baseline documented.
- No contradictory traits included.
- No vague phrasing like “kind of” or “sometimes.”

---

# Gate Behavior

FAIL if:

- Appearance is ambiguous.
- Behavioral profile is generic.
- Knowledge baseline missing.
- No forbidden drift rules defined.
- Traits conflict internally.

PASS when:

- Visual anchors are clear.
- Personality baseline stable.
- Downstream prompt-packager can operate without guessing.
- QC team can detect drift objectively.

---

# Escalation Policy

Escalate to Judgment Tier if:

- Character complexity high.
- Psychological contradictions exist.
- Identity nuance critical to narrative.
- Multiple trait interpretations possible.

---

# Common Failure Modes

- Generic appearance description.
- Overloaded personality traits.
- Conflicting emotional baseline.
- No defined knowledge state.
- Allowing silent wardrobe changes.
- Adding “cool” traits later without justification.

---

# Related Skills

- script-breakdown
- character-psychology
- continuity-supervisor
- world-state-tracker
- prompt-packager
- qc-grader
