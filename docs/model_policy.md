# Model Policy

This document defines how models are selected, routed, escalated, and constrained across the system.

This framework is model-agnostic by design.

Skills define required capability tiers.
`model-router` selects the cheapest viable model.

No skill may hardcode a vendor.

---

# 1. Core Principles

1. Always use the cheapest viable tier.
2. Escalate only when gates fail.
3. Never escalate silently.
4. Document every routing decision.
5. Premium tier usage must be justified.
6. Tier decisions must consider cost and regen risk.

Model selection is strategic, not emotional.

---

# 2. Capability Tiers

The system defines capability tiers independent of vendor.

---

## Tier 1 — Throughput

Purpose:
- Structured extraction
- Formatting
- CSV generation
- JSON state updates
- Basic transformation
- Deterministic prompt packaging

Examples:
- script-breakdown
- world-state-tracker
- prompt-packager
- run-logger

Characteristics:
- Low cost
- High speed
- Minimal reasoning depth

---

## Tier 2 — Judgment

Purpose:
- Psychological nuance
- Plausibility arbitration
- Narrative evaluation
- QC grading
- Audience simulation

Examples:
- character-psychology
- plausibility-auditor
- audience-simulator
- qc-grader
- regen-analyzer

Characteristics:
- Moderate cost
- Analytical reasoning
- Context integration

---

## Tier 3 — Premium / Arbitration

Purpose:
- Structural rewrites
- Complex red-team analysis
- Emotional turning-point validation
- High-risk escalation
- Ambiguity resolution

Examples:
- narrative-red-team (complex cases)
- story-architect (high-level arbitration)
- continuity-supervisor (multi-scene conflict resolution)

Characteristics:
- High cost
- Deep reasoning
- Reserved for critical moments

---

## Vision Tier

Purpose:
- Spatial validation
- Complex composition arbitration
- Storyboard evaluation
- High-detail visual reasoning

Examples:
- storyboard-generator (complex scenes)
- QC for subtle facial drift
- Complex blocking arbitration

---

## Research Tier

Purpose:
- Domain expertise
- Citation-backed validation
- Historical nuance
- Technical verification

Examples:
- research-agent
- cultural-check (complex cases)

---

# 3. Default Tier Mapping by Skill

## Narrative Layer

- story-architect → Tier 2 (Tier 3 if structural conflict)
- script-breakdown → Tier 1
- character-psychology → Tier 2
- dialogue-consistency-check → Tier 2

## Validation Layer

- research-agent → Research Tier
- plausibility-auditor → Tier 2
- cultural-check → Tier 2–Research
- narrative-red-team → Tier 3 (Tier 2 for light pass)
- audience-simulator → Tier 2

## Continuity Layer

- character-lock → Tier 2
- set-lock → Tier 2
- voice-lock → Tier 2
- world-state-tracker → Tier 1
- continuity-supervisor → Tier 2

## Production Layer

- shot-planner → Tier 2
- prompt-packager → Tier 1
- storyboard-generator → Vision Tier
- qc-grader → Tier 2
- regen-analyzer → Tier 2

## Governance Layer

- cost-optimizer → Tier 1–2
- model-router → Tier 1
- budget-gates → Tier 1
- run-logger → Tier 1

---

# 4. Visual Model Routing

Hero-tier classification drives visual model tier.

Hero-tier A:
- Premium visual model
- High identity stability
- Higher resolution allowed

Hero-tier B:
- Mid-tier model
- Balanced cost vs quality

Hero-tier C:
- Low-cost model
- Background / coverage

Never render all shots at premium tier.

---

# 5. Escalation Rules

Escalation is allowed only when:

- Gate FAIL persists
- Regen limit reached
- Emotional nuance insufficient
- Visual drift unresolved
- Ambiguity cannot be resolved at current tier

Escalation must:

- Be logged
- Include cost impact estimate
- Be approved by budget-gates if near cap

---

# 6. De-Escalation Rules

Tier should be reduced when:

- Task repetitive
- Structured output only
- Formatting only
- No nuance required
- Shot classified as hero-tier C

Premium tier is not default.

---

# 7. Vendor Neutrality Rule

Skills may not reference specific model names.

Instead, they reference:

- Tier 1
- Tier 2
- Tier 3
- Vision Tier
- Research Tier

Mapping of vendors to tiers is external configuration.

This allows:

- Swapping providers
- Running local models
- Optimizing for price changes
- Avoiding vendor lock-in

---

# 8. Tier Quotas (Recommended)

Example production quotas:

- Tier 3 usage ≤ 15% of narrative skills
- Premium visual tier ≤ 25% of shots
- Research tier limited to fact-dependent scenes

Quotas prevent drift toward expensive defaults.

---

# 9. Model Switching Mid-Project

Switching providers requires:

- Routing decision artifact
- QC validation sample
- Cost comparison
- Lock consistency test

Silent switching prohibited.

---

# 10. Failure Patterns & Tier Signals

Escalate tier when:

- QC repeatedly fails for identity drift
- Emotional turning point feels flat
- Structural contradictions unresolved
- Audience simulation inconsistent

Do NOT escalate when:

- Prompt ambiguous
- Lock incomplete
- Shot too complex
- Regen-analyzer not run
- Cost-optimizer not consulted

Escalation is last resort.

---

# 11. Logging Requirements

Every routing decision must produce:

`ROUTING_DECISION_<TASK>_v###.md`

And must log:

- Tier selected
- Justification
- Cost estimate
- Escalation condition

No undocumented routing allowed.

---

# 12. Philosophy

Model power is a tool, not a crutch.

Overpowered models hide structural weaknesses.
Underpowered models create frustration.

Correct routing creates:

- Stability
- Cost efficiency
- Reproducibility
- Scale

This framework optimizes for discipline, not hype.
