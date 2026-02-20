# Agent Contract

This document defines the non-negotiable rules governing all skills in this repository.

If a skill violates this contract, it is considered invalid.

---

# 1. Skills Are Deterministic Units

Each skill must:

- Declare invocation conditions.
- Declare required inputs.
- Produce versioned artifacts.
- Define PASS / FAIL gate behavior.
- Define escalation conditions.
- Log execution via run-logger.

Skills may not:
- Rely on chat memory.
- Invent unstated inputs.
- Skip artifact creation.
- Bypass gate enforcement.

---

# 2. Artifact-Based Memory

The system does not rely on conversation history.

It relies on explicit, versioned artifacts.

All state must exist in artifacts such as:

- `CHAR_*_LOCK_v###`
- `SET_*_LOCK_v###`
- `VOICE_*_LOCK_v###`
- `WORLD_STATE_v###`
- `STATE_DIFF_*_v###`
- `TRUTH_*_v###`
- `PLAUS_*_v###`
- `QC_BATCH_*_v###`
- `REGEN_RULES_v###`
- `COST_REPORT_*_v###`
- `BUDGET_STATUS_v###`
- `RUN_LOG_v###`

If it is not in an artifact, it does not exist.

---

# 3. Versioning Rules

All artifacts must:

- Use semantic version format `v###`
- Never overwrite previous versions
- Increment sequentially
- Be append-only in logs

Example:
- `WORLD_STATE_v001.json`
- `WORLD_STATE_v002.json`

No artifact may be silently replaced.

---

# 4. Gate Enforcement

Every skill must define:

- Explicit PASS criteria
- Explicit FAIL conditions
- Escalation triggers

Progression rule:

> No downstream skill may execute if upstream gate = FAIL.

If FAIL occurs:
- Loop must trigger (revision or escalation).
- Reason must be logged.

---

# 5. Escalation & Model Tiering

Skills do not hardcode vendor models.

They define required **capability tiers**:

- Tier 1: Throughput (formatting, extraction)
- Tier 2: Judgment (analysis, nuance)
- Tier 3: Premium / Vision (complex arbitration, hero visuals)
- Research Tier (domain verification)
- Vision Tier (complex spatial validation)

Model selection is handled by `model-router`.

No skill may bypass routing logic.

---

# 6. Lock Discipline

Lock artifacts are immutable constraints.

Lock types:
- Character Lock
- Set Lock
- Voice Lock
- (Optional) Style Lock

Rules:
- Locks cannot be modified without explicit new version.
- Drift must be treated as FAIL.
- Locks must be included verbatim in prompt-packager.
- QC must compare output against locks.

---

# 7. World-State Discipline

World-state is canonical memory.

Rules:
- Every scene must produce `STATE_DIFF`.
- `WORLD_STATE` must update sequentially.
- No character may use knowledge not recorded.
- Injuries persist unless healed explicitly.
- Props cannot teleport.

World-state contradictions = FAIL.

---

# 8. Regeneration Control

Blind retries are prohibited.

After 2 failed attempts:
- `regen-analyzer` must execute.
- Root cause must be documented.
- Prompt adjustments must be versioned.
- Cost impact must be evaluated.

Infinite loops are not allowed.

---

# 9. Budget Governance

Budget caps are enforceable.

Rules:
- Cost must be projected before batch run.
- Regen multiplier must be applied.
- Premium tier usage must be justified.
- Budget-gates can trigger HARD STOP.

No skill may override budget-gates.

---

# 10. Logging Requirements

Every skill execution must generate a log entry.

Minimum logging fields:
- skill_name
- model_used
- tier
- artifact_created
- outcome
- regen_count
- cost_estimate
- timestamp

Logs are append-only.

No silent execution allowed.

---

# 11. Loop Integrity

The system is loop-driven, not linear.

Common loops:

Validation Loop:
research → plausibility → revise

Continuity Loop:
world-state → continuity-supervisor → revise

Production Loop:
generate → QC → regen-analyzer → repackage → generate

Cost Loop:
cost-projection → simplify → reroute → regenerate

If a loop exists, it must be explicitly documented.

---

# 12. No Silent Mutation Rule

No skill may:

- Modify upstream artifacts silently.
- Change lock data inline.
- Alter world-state without diff.
- Escalate model tier without routing.

All mutation must:
- Create new version.
- Be logged.
- Justify change.

---

# 13. Skill Quality Requirements

Each skill must contain:

- Trigger conditions
- Required inputs
- Required artifacts
- Process steps
- Evaluation checklist
- Gate behavior
- Escalation policy
- Common failure modes
- Related skills

Skills missing these sections are incomplete.

---

# 14. Human Override

Humans may override any decision.

However:
- Override must be logged.
- Cost impact documented.
- Lock violations documented.
- Version incremented.

---

# 15. System Philosophy

This repository is not a prompt collection.

It is:

- A production operating system
- A drift prevention framework
- A cost-governed pipeline
- A model-agnostic architecture

If a change weakens discipline, it violates the contract.
