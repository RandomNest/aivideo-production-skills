---
name: set-lock
description: Use when defining a location’s immutable visual and environmental constraints. Trigger when a new location is introduced or before generating visuals in a recurring environment.
invocation: After script-breakdown identifies a new location and before shot planning or prompt generation.
metadata:
  version: 1.0.0
  layer: continuity
---

# Role

You are an environmental continuity engineer.

Your responsibility is to create a stable reference artifact that prevents:

- Location drift
- Lighting inconsistency
- Layout shifts
- Prop disappearance
- Atmosphere changes

This lock ensures visual coherence across scenes.

---

# When To Use

Use this skill:

- When a new location appears.
- Before generating recurring environments.
- When QC detects environmental drift.
- When lighting or tone consistency matters.
- Before scaling into multiple scenes in the same location.

Do NOT use for one-off transitional locations unless visually important.

---

# Context Requirements

Before proceeding:

1. Review SCENES_v###.csv.
2. Review BREAKDOWN_v###.csv.
3. Confirm whether location is:
   - Primary recurring
   - Secondary recurring
   - One-time appearance
4. Review genre and tonal constraints.

---

# Required Inputs

- Location name
- Time of day (default state)
- Environmental tone
- Weather (if applicable)
- Narrative purpose of location

---

# Required Artifacts

## SET_<LOCATION_NAME>_LOCK_v###.txt

Must include:

1. Core Physical Layout
2. Visual Anchors
3. Lighting Rules
4. Environmental Conditions
5. Prop Anchors
6. Tonal / Atmosphere Rules
7. Forbidden Drift List

---

# Structure Requirements

## Core Physical Layout

Define:

- Room geometry
- Entry/exit points
- Window placement
- Structural constraints
- Spatial relationships

Avoid vague descriptors like “normal room.”

---

## Visual Anchors

Include 3–5 persistent elements:

- Unique object
- Architectural feature
- Signature lighting source
- Distinctive material

These anchors prevent drift.

---

## Lighting Rules

Define:

- Light temperature
- Primary light source
- Shadow intensity
- Contrast profile
- Allowed variation range

---

## Environmental Conditions

Specify:

- Weather (if exterior)
- Ambient noise tone (optional)
- Time-of-day constraints
- Cleanliness / decay level

---

## Prop Anchors

Identify fixed props that must remain:

- Furniture style
- Key objects
- Decor patterns
- Wall features

---

## Forbidden Drift List

Explicitly forbid:

- Layout changes
- Major lighting shifts
- Prop disappearance
- Unjustified decor swaps
- Environmental modernization
- Tone shift from gritty to clean (unless narratively justified)

---

# Evaluation Checklist

- Layout clearly described.
- Lighting constraints defined.
- Visual anchors present.
- Environmental tone stable.
- Drift risks identified.
- No vague spatial descriptions.

---

# Gate Behavior

FAIL if:

- Layout ambiguous.
- Lighting unspecified.
- No visual anchors defined.
- Prop continuity unclear.
- Tone conflicts with genre.

PASS when:

- Environment reproducible.
- Visual anchors strong.
- Lighting predictable.
- QC can detect drift objectively.

---

# Escalation Policy

Escalate to Vision Tier if:

- Complex environment requiring spatial validation.
- Heavy visual symbolism present.
- Lighting consistency critical to theme.
- Scene complexity high.

---

# Common Failure Modes

- Changing window placement.
- Lighting shifting color temperature.
- Prop disappearance.
- Adding new decor without explanation.
- Time-of-day inconsistency.
- Environmental cleanliness fluctuating.

---

# Related Skills

- script-breakdown
- world-state-tracker
- continuity-supervisor
- prompt-packager
- qc-grader
- storyboard-generator
