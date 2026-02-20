---
name: skill-name
description: Clear description of when this skill should be used. Include trigger phrases and operational context.
invocation: Define exactly when this skill runs in the pipeline.
metadata:
  version: 1.0.0
  layer: narrative | validation | continuity | production | governance | observability
---

# Role

You are a [clear functional role description].

Your responsibility is to:

- Define purpose clearly
- Prevent specific failure types
- Produce deterministic artifacts
- Enforce gate discipline

You do not:
- Rely on chat memory
- Invent unstated context
- Modify upstream artifacts silently
- Skip artifact versioning

---

# When To Use

Use this skill when:

- Trigger condition 1
- Trigger condition 2
- Trigger condition 3

Do NOT use when:

- Out-of-scope case 1
- Upstream gate has failed
- Required inputs missing

---

# Context Requirements

Before proceeding:

1. List required upstream artifacts
2. List relevant locks
3. Confirm world-state version
4. Confirm prior gate PASS
5. Confirm routing tier selection

If any required input is missing → FAIL.

---

# Required Inputs

Explicitly list:

- Input 1
- Input 2
- Input 3

Inputs must be artifact-based where possible.

If input is implicit, document assumption explicitly.

---

# Required Artifacts

List all artifacts produced.

Use proper versioning format:

## 1. ARTIFACT_NAME_v###.ext

Describe structure requirements.

## 2. OPTIONAL_ARTIFACT_v###.ext

Only include if condition met.

No unversioned artifacts allowed.

---

# Process

1. Step 1 (deterministic action)
2. Step 2 (validation)
3. Step 3 (analysis or transformation)
4. Step 4 (artifact creation)
5. Step 5 (self-check)

Avoid vague instructions.

---

# Evaluation Checklist

Must include:

- All required inputs present
- No silent mutation
- Artifact naming correct
- Version incremented
- Schema compliance verified
- Gate criteria evaluated

Checklist must be explicit and auditable.

---

# Gate Behavior

## FAIL If:

- Define clear failure conditions
- Lock violation detected
- Schema inconsistency
- Missing required input
- Budget constraint violated (if applicable)

## PASS When:

- Clear criteria met
- Artifact created
- Downstream skills can proceed safely

No ambiguous PASS states.

---

# Escalation Policy

Escalate to higher model tier if:

- Defined ambiguity threshold
- Complex arbitration required
- Emotional nuance critical
- Structural conflict unresolved

Escalation must:

- Be logged
- Justify cost impact
- Respect budget-gates

De-escalate when task is mechanical.

---

# Loop Integration

Define which loop this skill belongs to:

- Narrative Loop
- Validation Loop
- Continuity Loop
- Production Loop
- Cost Loop
- Observability Loop

Define what triggers re-entry into the loop.

---

# Common Failure Modes

List realistic, concrete failure examples.

Examples:

- Drift due to incomplete lock
- Ambiguous schema keys
- Overwriting artifact
- Blind regen
- Escalating prematurely
- Ignoring budget constraint

This section prevents contributor naïveté.

---

# Related Skills

List upstream and downstream dependencies.

Example:

- Upstream: script-breakdown
- Downstream: world-state-tracker
- Governance: model-router
- Logging: run-logger

Always include run-logger if artifact created.

---

# Logging Requirements

Must log:

- skill_name
- model tier used
- artifact version created
- outcome (PASS / FAIL)
- regen_count (if applicable)
- estimated cost (if applicable)

No execution without logging.

---

# Philosophy Reminder

This skill exists to:

- Reduce entropy
- Increase determinism
- Improve reproducibility
- Control cost
- Prevent drift

If a change weakens discipline, it violates the system contract.
