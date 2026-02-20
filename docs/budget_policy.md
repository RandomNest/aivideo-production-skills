# Budget Policy

This document defines how cost is projected, monitored, enforced, and escalated within the AI Video Production Skills framework.

This system is designed to scale to feature-length projects.  
Without cost governance, it will collapse under regeneration loops.

---

# 1. Core Principles

1. Cost must be projected before generation.
2. Regen multipliers must be applied.
3. Premium model usage must be justified.
4. Budget caps are enforceable.
5. No silent tier escalation.
6. No infinite regeneration loops.

If cost discipline is bypassed, the system contract is violated.

---

# 2. Cost Categories

## A. Narrative & Validation Cost
- story-architect
- narrative-red-team
- plausibility-auditor
- audience-simulator
- research-agent

Typically low relative to production cost.

## B. Production Cost
- storyboard generation
- video generation
- audio generation
- regen attempts

Highest risk category.

## C. Governance Cost
- QC passes
- routing decisions
- logging

Low cost but mandatory.

---

# 3. Cost Projection Requirements

Before batch production:

`cost-optimizer` must generate:

- Total planned duration (seconds)
- Per-tier cost estimate
- Regen multiplier estimate
- Tier distribution breakdown
- Projected total cost

Projection formula:

Total Duration × Cost Per Second × Regen Multiplier

Regen multipliers:

Low risk → 1.1x  
Medium risk → 1.3x  
High risk → 1.6x+  

Multiplier must be justified.

---

# 4. Budget Caps

Budgets must be defined at:

- Project level
- Scene level (optional)
- Shot level (recommended)

Example:

- Project Cap: $15,000
- Per Scene Cap: $1,000
- Per Shot Cap: $200

Caps are configurable but mandatory.

---

# 5. Enforcement Thresholds

## 90% of Budget

- Warning state
- Must rerun cost-optimizer
- Tier allocation review required

## 100% of Budget

- HARD STOP
- No further generation allowed
- Requires structural simplification
- Human override required and logged

---

# 6. Regen Attempt Limits

Default recommended limits:

- Hero-tier A: 3 attempts
- Hero-tier B: 2 attempts
- Hero-tier C: 2 attempts

After limit reached:

1. regen-analyzer must run
2. Shot must simplify OR
3. Tier escalation must be justified
4. budget-gates must re-evaluate impact

Blind retries are prohibited.

---

# 7. Premium Tier Usage Rules

Premium / Vision Tier may only be used when:

- Shot classified as Hero-tier A
- Emotional stakes critical
- QC failure persists at lower tier
- Cost impact documented

Premium tier usage must not exceed defined quota.

Example quota:
- ≤ 25% of total shot count

---

# 8. Proxy-First Requirement

All projects must:

- Generate proxy-resolution outputs first
- Validate via QC
- Escalate to final resolution only after PASS

Skipping proxy stage increases cost risk and violates discipline.

---

# 9. Structural Cost Reduction Options

When cost exceeds threshold, allowed interventions:

- Shorten shot duration
- Split complex shots
- Reduce character density
- Reduce camera movement
- Downgrade non-hero shots to lower tier
- Simplify blocking
- Reduce lighting complexity
- Convert complex shot to static coverage

Creative compromise must be logged.

---

# 10. Batch Efficiency Rules

To reduce cost:

- Group shots by set
- Group shots by lighting condition
- Avoid jumping between environments
- Avoid random shot ordering

Batch inefficiency increases regen multiplier.

---

# 11. Escalation Hierarchy

When cost issues arise:

1. cost-optimizer evaluates
2. model-router reassesses tier allocation
3. shot-planner simplifies geometry
4. regen-analyzer adjusts GenPack rules
5. budget-gates enforces

If still unresolved:
→ Human review required

---

# 12. Logging Requirements

All cost-related decisions must be logged in:

`RUN_LOG_v###.csv`

Must record:

- Tier used
- Estimated cost
- Actual cost (if available)
- Regen count
- Budget status at time of run

No undocumented spending allowed.

---

# 13. Human Override Policy

Human override allowed only if:

- Documented in run-log
- Budget impact recorded
- Justification written
- Version incremented

Override does not exempt logging.

---

# 14. Philosophy

This system is designed to:

- Scale sustainably
- Avoid emotional regeneration decisions
- Make cost visible
- Prevent silent overspend
- Enable rational tradeoffs

Creative ambition must coexist with financial discipline.

Budget governance is not optional.
