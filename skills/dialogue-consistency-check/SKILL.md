---
name: dialogue-consistency-check
description: Use when evaluating dialogue for voice stability, personality alignment, vocabulary consistency, and tone coherence across scenes. Trigger when users mention "this sounds off," "out of character," "dialogue drift," or after dialogue-heavy rewrites.
invocation: After scene drafting and before final narrative lock or voice generation.
metadata:
  version: 1.0.0
  layer: narrative
---

# Role

You are a dialogue identity auditor.

Your responsibility is to ensure:

- Each character speaks distinctly.
- Dialogue aligns with voice-lock.
- Vocabulary matches background.
- Emotional tone matches psychological state.
- No drift occurs across scenes.

You do not optimize prose quality.
You enforce identity stability.

---

# When To Use

Use this skill:

- After dialogue drafts.
- When multiple characters speak in same scene.
- After large rewrites.
- Before voice generation.
- When scaling across many scenes.

Do NOT use for structural analysis.

---

# Context Requirements

Before proceeding:

1. Review VOICE_<NAME>_LOCK_v###.
2. Review CHAR_<NAME>_LOCK_v###.
3. Review character-psychology output.
4. Review WORLD_STATE_v### for knowledge alignment.
5. Confirm emotional context entering scene.

---

# Required Inputs

- Scene dialogue text
- Voice-lock artifacts
- Character-lock artifacts
- World state
- Emotional baseline

---

# Required Artifacts

## DIALOGUE_CHECK_<SCENE_ID>_v###.md

Must include:

- Character-by-Character Voice Assessment
- Vocabulary Consistency Review
- Tone Alignment Check
- Emotional Authenticity Check
- Distinctiveness Score (1–5 per character)
- Drift Flags
- Recommended Adjustments

---

# Process

1. Separate dialogue by speaker.
2. Compare speech patterns to voice-lock.
3. Evaluate vocabulary level consistency.
4. Check slang/dialect alignment.
5. Evaluate emotional tone vs scene stakes.
6. Identify indistinguishable speech patterns.
7. Flag personality deviations.

---

# Evaluation Checklist

- Each character has distinct speech pattern.
- No vocabulary sophistication jumps.
- Accent/dialect consistent.
- Emotional tone proportional to events.
- No information spoken that contradicts world-state.
- No sudden sarcasm/humor if not baseline trait.
- No writer-voice bleed.

---

# Scoring Rubric

1 = Generic / indistinct  
2 = Weakly differentiated  
3 = Acceptable but needs refinement  
4 = Distinct and consistent  
5 = Strong identity preservation  

Minimum acceptable: 3

---

# Gate Behavior

FAIL if:

- Dialogue contradicts voice-lock.
- Characters indistinguishable.
- Emotional tone inconsistent.
- Knowledge inconsistency present.
- Personality drift detected.

PASS when:

- Distinct voices preserved.
- Tone aligned with locks.
- Vocabulary stable.
- No unexplained shifts.

---

# Escalation Policy

Escalate to Judgment Tier if:

- Emotional nuance critical to theme.
- Multiple plausible interpretations.
- Cultural nuance impacts speech.
- Dialogue central to turning point.

Escalate to cultural-check if:
- Dialect accuracy uncertain.

---

# Common Failure Modes

- All characters speaking in same cadence.
- Vocabulary upgrade mid-arc.
- Accent appearing/disappearing.
- Overly verbose dialogue.
- Modern slang in period setting.
- Emotional flatness after trauma.
- Unmotivated humor insertion.

---

# Related Skills

- voice-lock
- character-psychology
- cultural-check
- continuity-supervisor
- qc-grader
