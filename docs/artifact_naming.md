# Artifact Naming Conventions

This document defines how artifacts must be named, versioned, and structured across the system.

If artifact naming is inconsistent, the system becomes untraceable.

---

# 1. Core Principles

All artifacts must:

- Be versioned using `v###`
- Never overwrite previous versions
- Use consistent prefixes
- Be machine-parsable
- Reflect the skill that produced them
- Be append-only (where applicable)

If it is not versioned, it is invalid.

---

# 2. Version Format

Version format:

v001  
v002  
v003  

Rules:

- Always 3 digits.
- Increment sequentially.
- Never skip versions.
- Never reuse version numbers.
- Never overwrite prior version.

Correct:
- `WORLD_STATE_v001.json`
- `WORLD_STATE_v002.json`

Incorrect:
- `WORLD_STATE_v1.json`
- `WORLD_STATE_final.json`
- `WORLD_STATE_latest.json`

---

# 3. Artifact Prefix Conventions

## Narrative Layer

- `BEATS_v###.md`
- `SCENES_v###.csv`
- `BREAKDOWN_v###.csv`
- `PSYCH_<SCENE_ID>_v###.md`
- `DIALOGUE_CHECK_<SCENE_ID>_v###.md`

---

## Validation Layer

- `TRUTH_<SCENE_ID>_v###.md`
- `PLAUS_<SCENE_ID>_v###.md`
- `CULTURE_<SCENE_ID>_v###.md`
- `REDTEAM_<TARGET>_v###.md`
- `AUDIENCE_<TARGET>_v###.md`

---

## Continuity Layer

- `CHAR_<NAME>_LOCK_v###.txt`
- `SET_<LOCATION_NAME>_LOCK_v###.txt`
- `VOICE_<NAME>_LOCK_v###.txt`
- `WORLD_STATE_v###.json`
- `STATE_DIFF_<SCENE_ID>_v###.json`
- `CONTINUITY_REPORT_<TARGET>_v###.md`

---

## Production Layer

- `SHOTLIST_<SCENE_ID>_v###.csv`
- `GENPACK_<SHOT_ID>_v###.txt`
- `STORYBOARD_<SHOT_ID>_v###.png`
- `STORYBOARD_REPORT_<SHOT_ID>_v###.md`
- `QC_BATCH_<SCENE_OR_RUN>_v###.csv`
- `REGEN_RULES_v###.md`

---

## Governance Layer

- `COST_REPORT_<TARGET>_v###.md`
- `ROUTING_DECISION_<TASK>_v###.md`
- `BUDGET_STATUS_v###.md`
- `RUN_LOG_v###.csv`

---

# 4. Scene and Shot ID Format

Scene IDs:

S01  
S02  
S03  

Shot IDs:

S01_SH01  
S01_SH02  
S02_SH01  

Rules:

- Scene prefix always included.
- Shot numbering resets per scene.
- Zero-padded for sorting consistency.

Correct:
- `GENPACK_S01_SH03_v002.txt`

Incorrect:
- `GENPACK_SH3.txt`
- `GENPACK_scene1_shot1.txt`

---

# 5. Target Naming Rules

Where `<TARGET>` appears, use:

- Scene ID (e.g., S03)
- Act name (ACT_1)
- Episode ID (E01)
- Full project (PROJECT)

Examples:
- `REDTEAM_ACT_1_v001.md`
- `AUDIENCE_PROJECT_v002.md`
- `CONTINUITY_REPORT_S02_v003.md`

---

# 6. Lock Naming Rules

Lock artifacts must:

- Use uppercase prefix
- Include subject name in uppercase
- Replace spaces with underscores

Examples:

Correct:
- `CHAR_ALEX_LOCK_v001.txt`
- `SET_ABANDONED_WAREHOUSE_LOCK_v001.txt`
- `VOICE_MARIA_LOCK_v002.txt`

Incorrect:
- `alex_character.txt`
- `warehouse_lock.txt`
- `maria_voice.txt`

---

# 7. JSON Artifact Structure Rules

All JSON artifacts must:

- Be valid JSON
- Use stable key ordering
- Avoid nested arbitrary structures
- Be schema-consistent across versions

Core JSON artifacts:

- WORLD_STATE
- STATE_DIFF

Top-level keys must remain stable across versions.

---

# 8. CSV Artifact Rules

CSV artifacts must:

- Include headers
- Maintain column order
- Avoid dynamic column renaming
- Avoid blank rows
- Avoid merged cells

CSV used for:

- SCENES
- BREAKDOWN
- SHOTLIST
- QC_BATCH
- RUN_LOG

Column structure changes require version bump.

---

# 9. File Extensions

Use:

.md → human-readable structured analysis  
.txt → lock artifacts / structured prompts  
.csv → structured tabular data  
.json → canonical system state  
.png → storyboard visual  

Do not mix types.

---

# 10. No “Final” Files

Prohibited suffixes:

- _final
- _new
- _latest
- _updated

Version numbers replace these.

Correct:
- `GENPACK_S01_SH02_v003.txt`

Incorrect:
- `GENPACK_S01_SH02_final.txt`

---

# 11. Directory Structure

Recommended layout:
project/
narrative/
validation/
continuity/
production/
governance/
artifacts/

Or flat structure grouped by prefix.

Consistency is more important than nesting depth.

---

# 12. Enforcement Rule

If an artifact:

- Is unversioned
- Violates prefix rules
- Breaks schema consistency
- Overwrites prior version

It violates the system contract.

---

# 13. Philosophy

Naming conventions are not cosmetic.

They enable:

- Deterministic orchestration
- Programmatic parsing
- Auditability
- Cost traceability
- Reproducibility

If naming drifts, the system collapses.
