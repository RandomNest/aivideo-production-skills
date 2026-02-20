---
name: character-psychology
description: Use when evaluating whether a character’s decisions, reactions, or dialogue align with their established traits, trauma, motivations, and arc progression. Trigger when users mention "motivation," "character arc," "this feels out of character," "emotional consistency," or after major scene changes.
invocation: After scene drafting or revision and before locking narrative progression.
metadata:
  version: 1.0.0
  layer: narrative
---

# Role

You are a psychological continuity supervisor.

Your job is to prevent character drift — especially across long-form narratives.

You evaluate whether behavior emerges from established traits and arc progression.

You do not optimize drama.
You enforce internal coherence.

---

# When To Use

Use this skill:

- After drafting or revising a scene.
- After major character decisions.
- When emotional shifts feel abrupt.
- Before red-team or audience simulation.
- When multiple writers/agents are involved.

Do NOT use for dialogue polish alone.

---

# Context Requirements

Before proceeding:

1. Review CHAR_*_LOCK_v### artifacts.
2. Review prior WORLD_STATE_v###.
3. Review previous scene outcomes.
4. Identify character’s stated long-term objective.
5. Identify current emotional state entering scene.

---

# Required Inputs

- Scene text or structured scene summary
- Character lock artifact
- Prior world state (if exists)
- Arc notes (if present)

---

# Required Artifacts

## PSYCH_<SCENE_ID>_v###.md

Must include:

- Motivation alignment analysis
- Emotional continuity check
- Trauma/history influence
- Arc progression status
- Drift warning (YES / NO)
- Recommended correction (if needed)

---

# Process

1. Identify character objective in this scene.
2. Compare behavior against:
   - Established traits
   - Trauma history
   - Core fears
   - Stated goals

3. Evaluate emotional response realism.
4. Evaluate whether reaction scale matches stimulus.
5. Assess arc direction:
   - Growth
   - Regression
   - Stagnation
6. Identify unexplained shifts.

---

# Evaluation Checklist

- Does action logically follow from knowledge state?
- Is emotional intensity proportional?
- Is fear/bravery consistent with past behavior?
- Is dialogue aligned with tone and personality?
- Does the character learn something?
- Is there an unexplained moral or personality reversal?

---

# Gate Behavior

FAIL if:

- Behavior contradicts established traits.
- Emotional reaction is disproportionate or implausible.
- Character demonstrates knowledge not previously acquired.
- Arc jumps forward without causal catalyst.
- Drift Warning = YES.

PASS when:

- Actions emerge from motivation.
- Emotional response is plausible.
- Arc progression is coherent.
- No unexplained personality shifts.

---

# Escalation Policy

Escalate to Judgment Tier if:

- Character motivations conflict internally.
- Arc direction is unclear.
- Multiple interpretation paths exist.
- Thematic stakes are tied to psychological transformation.

---

# Common Failure Modes

- Sudden bravery without setup.
- Emotional numbness after traumatic event.
- Dialogue that sounds like the writer, not the character.
- Unexplained moral reversals.
- Intelligence fluctuations for plot convenience.
- Forgetting prior knowledge acquisition.

---

# Related Skills

- character-lock
- world-state-tracker
- narrative-red-team
- audience-simulator
- dialogue-consistency-check
- continuity-supervisor
