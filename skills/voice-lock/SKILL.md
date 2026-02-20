---
name: voice-lock
description: Use when defining a character’s vocal identity for dialogue, narration, or audio generation. Trigger when a character speaks, when generating voiceover, or when consistent vocal performance is required across scenes.
invocation: After character-lock and before dialogue generation or audio synthesis.
metadata:
  version: 1.0.0
  layer: continuity
---

# Role

You are a vocal continuity engineer.

Your responsibility is to define and preserve:

- Vocal tone
- Cadence
- Accent
- Speech patterns
- Emotional delivery style

This lock ensures character identity remains stable in spoken dialogue and narration.

---

# When To Use

Use this skill:

- When a character first speaks.
- Before generating voiceover.
- When audio synthesis is planned.
- When QC detects vocal inconsistency.
- When scaling dialogue across multiple scenes.

Do NOT use for silent characters.

---

# Context Requirements

Before proceeding:

1. Review CHAR_<NAME>_LOCK_v###.
2. Review character-psychology output.
3. Identify emotional baseline.
4. Identify cultural / regional background (if relevant).
5. Confirm whether:
   - Dialogue-driven character
   - Sparse speaker
   - Narrator role

---

# Required Inputs

- Character lock artifact
- Emotional baseline
- Cultural / regional context
- Age range
- Narrative tone

---

# Required Artifacts

## VOICE_<NAME>_LOCK_v###.txt

Must include:

1. Vocal Tone Profile
2. Cadence & Rhythm
3. Accent / Dialect Specification
4. Emotional Delivery Range
5. Speech Pattern Constraints
6. Forbidden Drift List
7. (Optional) External Voice ID Reference

---

# Structure Requirements

## Vocal Tone Profile

Define:

- Pitch range (low / mid / high)
- Timbre (warm, gravelly, sharp, etc.)
- Energy level (restrained / animated)

Avoid vague descriptors like “normal voice.”

---

## Cadence & Rhythm

Specify:

- Sentence length tendencies
- Pause patterns
- Speed (slow / moderate / fast)
- Interruptions / hesitations

---

## Accent / Dialect

If applicable:

- Region
- Strength of accent
- Vocabulary tendencies
- Slang level

Must align with cultural-check output.

---

## Emotional Delivery Range

Define:

- Default emotional state
- Upper intensity limit
- Lower emotional baseline
- Reaction patterns under stress

---

## Speech Pattern Constraints

Include:

- Vocabulary complexity level
- Swearing frequency (if any)
- Figurative language usage
- Directness vs indirectness

---

## Forbidden Drift List

Explicitly forbid:

- Accent switching
- Sudden vocabulary sophistication shift
- Emotional intensity spikes without cause
- Tone shifting from restrained to theatrical
- Speech speed inconsistencies

---

# Evaluation Checklist

- Vocal identity distinct.
- Tone matches personality.
- Accent consistent with background.
- Emotional range defined.
- Drift constraints explicit.
- Downstream dialogue generation constrained.

---

# Gate Behavior

FAIL if:

- Vocal tone ambiguous.
- Accent unspecified where culturally relevant.
- Emotional delivery undefined.
- No forbidden drift rules.
- Voice conflicts with character-psychology baseline.

PASS when:

- Voice identity reproducible.
- Dialogue style consistent.
- Emotional range controlled.
- QC can evaluate vocal drift objectively.

---

# Escalation Policy

Escalate to Judgment Tier if:

- Accent nuance culturally sensitive.
- Emotional range central to narrative.
- Narrator voice must carry thematic weight.
- Tone conflicts detected across scenes.

---

# Common Failure Modes

- Accent disappears mid-story.
- Vocabulary shifts randomly.
- Emotional tone inconsistent with scene stakes.
- Overly theatrical speech in grounded genre.
- Dialogue indistinguishable between characters.
- Sudden slang insertion.

---

# Related Skills

- character-lock
- character-psychology
- dialogue-consistency-check
- cultural-check
- qc-grader
