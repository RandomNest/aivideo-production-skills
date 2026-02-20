# How to Run This System

This guide explains how to execute the AI Video Production Skills framework in a real project.

This system is:

- Model-agnostic
- Agent-compatible
- Artifact-driven
- Loop-enforced
- Cost-governed

You can run it:

- Manually (human-in-the-loop)
- With a single orchestrator agent
- With multi-agent automation
- With local + remote models
- With Google Drive or filesystem storage

This document describes the canonical execution flow.

---

# 1. Project Setup

Create a project directory:
my-film-project/
narrative/
validation/
continuity/
production/
governance/
logs/


Copy or reference skill definitions from the repo.

Define:

- Budget cap
- Model tier mapping (vendor → tier)
- Regen limits
- Resolution tiers (proxy vs final)

---

# 2. Phase 1 — Narrative Foundation

## Step 1: story-architect

Create:
- `BEATS_v001.md`
- `SCENES_v001.csv`

Gate:
- Structural PASS required

---

## Step 2: script-breakdown

Create:
- `BREAKDOWN_v001.csv`

Gate:
- All continuity risks documented

---

## Step 3: character-psychology

Create:
- `PSYCH_<SCENE_ID>_v001.md`

Gate:
- Emotional logic coherent

---

## Step 4: narrative-red-team

Create:
- `REDTEAM_PROJECT_v001.md`

Gate:
- No major structural weaknesses

---

## Step 5: audience-simulator

Create:
- `AUDIENCE_PROJECT_v001.md`

Gate:
- Stakes clear
- Confusion minimized

If FAIL:
→ Revise BEATS  
→ Increment version  
→ Rerun loop  

Do not move to production until PASS.

---

# 3. Phase 2 — Validation Loop

For each scene:

## research-agent

Create:
- `TRUTH_S##_v001.md`

## plausibility-auditor

Create:
- `PLAUS_S##_v001.md`

## cultural-check (if needed)

Create:
- `CULTURE_S##_v001.md`

Gate:
- No high-risk realism issues

If FAIL:
→ Revise scene  
→ Rerun validation  

---

# 4. Phase 3 — Lock Creation

For each core entity:

## character-lock
→ `CHAR_<NAME>_LOCK_v001.txt`

## set-lock
→ `SET_<LOCATION>_LOCK_v001.txt`

## voice-lock
→ `VOICE_<NAME>_LOCK_v001.txt`

Locks must be created before generation begins.

Locks are immutable unless versioned.

---

# 5. Phase 4 — Continuity Initialization

Initialize:

`WORLD_STATE_v001.json`

Then for each scene:

1. Apply scene changes
2. Create `STATE_DIFF_S##_v001.json`
3. Generate `WORLD_STATE_v002.json`
4. Run continuity-supervisor

Gate:
- No contradictions

---

# 6. Phase 5 — Production Planning

For each scene:

## shot-planner
→ `SHOTLIST_S##_v001.csv`

(Optional)
## storyboard-generator
→ `STORYBOARD_S##_SH##_v001.png`
→ `STORYBOARD_REPORT_...`

Gate:
- Regen risk assessed
- Hero-tier assigned

---

# 7. Phase 6 — Generation Loop

For each shot:

## prompt-packager
→ `GENPACK_S##_SH##_v001.txt`

## Generate (proxy resolution first)

## qc-grader
→ `QC_BATCH_S##_v001.csv`

If FIX:
→ Minor tweak  
→ Regenerate  

If FAIL:
→ regen-analyzer  
→ Update `REGEN_RULES_v001.md`  
→ Update GenPack  
→ Regenerate  

Stop when QC PASS.

---

# 8. Phase 7 — Cost Governance

Before batch runs:

## cost-optimizer
→ `COST_REPORT_PROJECT_v001.md`

## model-router
→ `ROUTING_DECISION_PROJECT_v001.md`

## budget-gates
→ `BUDGET_STATUS_v001.md`

If budget near cap:
→ Simplify shots  
→ Downgrade tiers  
→ Split shots  

Hard stop at cap breach.

---

# 9. Logging (Always On)

After every skill:

## run-logger
→ `RUN_LOG_v001.csv`

Must record:

- Skill name
- Tier used
- Artifact created
- Outcome
- Cost
- Regen count

No step may execute without logging.

---

# 10. Proxy → Final Escalation

Only escalate to final resolution when:

- QC PASS at proxy
- Budget impact evaluated
- Premium tier justified (if used)

Never render final without proxy validation.

---

# 11. Human-in-the-Loop Mode

You can run manually:

1. Invoke skill definition
2. Generate artifact
3. Evaluate PASS/FAIL
4. Version increment
5. Log execution
6. Move to next stage

This is slower but safest for early projects.

---

# 12. Semi-Automated Mode

You may build an orchestrator that:

- Reads SCENES.csv
- Detects missing artifacts
- Executes required skills in order
- Checks PASS/FAIL markers
- Routes models via model-policy
- Logs results automatically

This is ideal for multi-scene projects.

---

# 13. Fully Automated Agent Mode

In advanced setups:

- Each skill becomes an agent
- Agents read required artifacts
- Agents emit versioned artifacts
- Central controller enforces gates
- budget-gates can stop entire system

This enables long-running productions.

---

# 14. Minimal Execution Order Summary

High-Level Order:

Narrative  
→ Validation  
→ Locks  
→ Continuity  
→ Shot Planning  
→ Generate  
→ QC  
→ Regen Loop  
→ Cost Enforcement  
→ Finalize  

At any FAIL:
→ Loop backward  
→ Version increment  
→ Log run  

---

# 15. Common Beginner Mistakes

- Generating before locks exist
- Skipping plausibility checks
- Not versioning artifacts
- Ignoring world-state updates
- Blindly regenerating
- Escalating models emotionally
- Not applying regen limits
- Not logging cost

Avoid these and the system remains stable.

---

# 16. What “Done” Looks Like

A finished project will contain:

- Versioned narrative artifacts
- Full world-state history
- Locked characters and sets
- Shotlists and GenPacks
- QC history
- Regen rule history
- Cost reports
- Full run logs

If those exist, the production is auditable and reproducible.

---

# 17. Philosophy

This is not a prompt workflow.

It is a production operating system.

Follow the gates.
Respect the loops.
Version everything.
Log everything.
Control cost.
Escalate intentionally.

The system works if you respect it.
