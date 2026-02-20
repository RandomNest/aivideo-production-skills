# Overview

AI Video Production Skills is a **model-agnostic**, **artifact-based**, **gate-enforced** framework for producing AI-assisted films and series at scale.

This is not a prompt library.

It is a reusable system for:
- preventing drift (character / set / voice)
- enforcing realism (truth + plausibility)
- maintaining continuity across scenes (world-state)
- minimizing regen waste (QC + regen learning)
- keeping costs bounded (budget gates + model routing)

---

## What “Skills” Are in This Repo

A **skill** is a modular unit of work designed to be executed by an agent (human or automated).

Each skill includes:
- when to invoke it (trigger conditions)
- required inputs and context
- required output artifacts (versioned)
- process steps and evaluation checklist
- pass/fail gate behavior
- escalation policy (model tiering)
- common failure modes
- related skills

Skills are designed to be composable so a pipeline can chain them without relying on chat memory.

---

## Core Design Principles

### 1) Artifact-Based Memory
The system does not rely on chat history.

It relies on external artifacts:
- locks (character / set / voice / style)
- world-state
- truth packets
- QC reports
- regen rules
- cost reports
- run logs

### 2) Gate Enforcement
Every stage defines PASS/FAIL criteria.
Progress happens only when gates pass.

### 3) Closed Loops, Not Linear Prompts
Failures trigger loops:
- research → plausibility → revise
- QC → regen rules → repackage → regenerate
- cost forecast → simplify → reroute models

### 4) Model-Agnostic
Skills never hardcode a vendor model.
They recommend a **tier**:
- Throughput
- Judgment
- Research
- Vision

### 5) Cost Discipline
Budgets and regen caps are enforced.
No silent overspend.

---

## The Skill Map (All Skills)

### Narrative Layer
- `story-architect`
- `script-breakdown`
- `character-psychology`
- `dialogue-consistency-check`

### Validation Layer
- `research-agent`
- `plausibility-auditor`
- `cultural-check`
- `narrative-red-team`
- `audience-simulator`

### Continuity Layer
- `character-lock`
- `set-lock`
- `voice-lock`
- `world-state-tracker`
- `continuity-supervisor`

### Production Layer
- `shot-planner`
- `prompt-packager`
- `storyboard-generator`
- `qc-grader`
- `regen-analyzer`

### Governance Layer
- `cost-optimizer`
- `model-router`
- `budget-gates`
- `run-logger`

---

## Typical End-to-End Flow

1. **Architecture**
   - story-architect → script-breakdown

2. **Locks**
   - character-lock / set-lock / voice-lock (and optional style lock)

3. **Truth & Realism**
   - research-agent → plausibility-auditor → cultural-check (as needed)

4. **Continuity**
   - world-state-tracker → continuity-supervisor

5. **Production Planning**
   - shot-planner → storyboard-generator (optional) → prompt-packager

6. **Generation + Quality**
   - generate → qc-grader → regen-analyzer (if needed)

7. **Cost Governance**
   - cost-optimizer → budget-gates → model-router (continuous)

8. **Observability**
   - run-logger logs every step

---

## What You Get if You Follow This System

- Characters that don’t change across scenes
- Sets that remain stable and reproducible
- Voices that keep identity over time
- Fewer regen cycles (lower cost)
- Better story durability (fewer plot holes and weak stakes)
- Clear “why” behind every decision via logs and artifacts
- The ability to swap models/providers without collapsing the pipeline

---

## Where to Go Next

- System diagram: `ARCHITECTURE.md`
- Skill contract rules: `agent_contract.md`
- Artifact naming conventions: `artifact_naming.md`
- Loop definitions: `loop_architecture.md`
- Model tiering: `model_policy.md`
- Budget enforcement: `budget_policy.md`
- Data spine schemas: `data_spine_templates.md`
