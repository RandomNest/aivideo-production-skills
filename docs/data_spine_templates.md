# Data Spine Templates

This document defines the canonical schemas used across the system. If schemas drift, orchestration becomes unreliable. All skills must conform to these templates unless versioned explicitly.

---

## 1. SCENES_v###.csv

**Produced by:** story-architect  
**Consumed by:** script-breakdown, shot-planner, continuity-supervisor

| Column | Type | Description |
|--------|------|-------------|
| scene_id | string | Unique scene identifier (e.g., S01) |
| summary | string | 1–3 sentence description |
| goal | string | Protagonist objective |
| conflict | string | Obstacle or resistance |
| outcome | string | State change |
| location | string | Canonical set name |
| time_of_day | string | Morning / Night / etc. |
| characters_present | string (comma-separated) | Character IDs |

---

## 2. BREAKDOWN_v###.csv

**Produced by:** script-breakdown  
**Consumed by:** lock skills, world-state-tracker

| Column | Description |
|--------|-------------|
| scene_id | |
| characters_present | |
| new_characters_introduced | |
| locations_used | |
| new_locations_introduced | |
| props_used | |
| new_props_introduced | |
| state_changes | |
| continuity_risks | |
| lock_requirements | |

---

## 3. WORLD_STATE_v###.json

**Produced by:** world-state-tracker  
**Consumed by:** continuity-supervisor, prompt-packager, QC
```json
{
  "timeline": {
    "current_scene": "",
    "elapsed_time": "",
    "global_notes": ""
  },
  "characters": {
    "CHAR_NAME": {
      "injuries": [],
      "knowledge": [],
      "inventory": [],
      "emotional_state": "",
      "location": ""
    }
  },
  "props": {
    "PROP_NAME": {
      "owner": "",
      "location": "",
      "status": ""
    }
  },
  "locations": {
    "SET_NAME": {
      "condition": "",
      "lighting_state": "",
      "notes": ""
    }
  },
  "rules": {
    "fictional_constraints": [],
    "modified_rules": []
  }
}
```

> Top-level keys must never change without a version bump.

---

## 4. STATE_DIFF_\<SCENE_ID\>_v###.json

**Produced by:** world-state-tracker
```json
{
  "scene_id": "S01",
  "character_updates": {},
  "prop_updates": {},
  "location_updates": {},
  "timeline_update": {},
  "rule_updates": {}
}
```

> STATE_DIFF must be applied sequentially to produce the next WORLD_STATE.

---

## 5. SHOTLIST_\<SCENE_ID\>_v###.csv

**Produced by:** shot-planner  
**Consumed by:** prompt-packager, cost-optimizer

| Column | Description |
|--------|-------------|
| shot_id | |
| scene_id | |
| duration_s | |
| camera_type | |
| blocking_summary | |
| set_id | |
| char_ids | |
| hero_tier (A/B/C) | |
| complexity_level (low/medium/high) | |
| regen_risk_estimate | |
| notes | |

---

## 6. QC_BATCH_\<TARGET\>_v###.csv

**Produced by:** qc-grader  
**Consumed by:** regen-analyzer, cost-optimizer

| Column | Description |
|--------|-------------|
| shot_id | |
| attempt_number | |
| face_consistency | |
| wardrobe_consistency | |
| set_continuity | |
| prop_accuracy | |
| lighting_consistency | |
| motion_integrity | |
| audio_consistency | |
| total_score | |
| verdict | |
| notes | |

---

## 8. GENPACK_\<SHOT_ID\>_v###.txt

**Produced by:** prompt-packager

Sections must appear in this exact order:
```
[STYLE]
[SET]
[CHARACTERS]
[ACTION]
[NEGATIVES / NO-DRIFT]
[SETTINGS]
```

---

## 9. COST_REPORT_\<TARGET\>_v###.md

**Produced by:** cost-optimizer

Must include: Total Duration, Tier Breakdown, Regen Multiplier, Projected Total Cost, High Risk Shots, Recommendations.

---

## 10. ROUTING_DECISION_\<TASK\>_v###.md

**Produced by:** model-router

Must include: Task Type, Tier Selected, Justification, Cost Impact, Escalation Conditions.

---

## 11. BUDGET_STATUS_v###.md

**Produced by:** budget-gates

Must include: Current Spend, Projected Spend, % Budget Used, Regen Count, Tier Usage, Enforcement Action.

---

## 12. Design Philosophy

These schemas exist to:

- Enable deterministic orchestration
- Allow programmatic parsing
- Support analytics
- Enable cost forecasting
- Prevent silent structural drift
- Make model swapping possible

If a schema changes, the version must increment and be documented. The data spine is the backbone of the system.

---

> **Next:** `docs/loop_architecture.md` — the closed-loop logic tying all 23 skills together.
