# Loop Architecture

AI Video Production Skills is not a linear pipeline.

It is a gated, loop-driven system designed to prevent:

- Narrative drift
- Continuity collapse
- Infinite regeneration
- Cost explosion
- Silent model escalation

This document defines the system loops and how they interact.

---

# 1. Why Loops Matter

Most AI workflows look like this:

Write → Generate → Fix → Regenerate → Hope

This system instead defines controlled loops with:

- Explicit PASS criteria
- Explicit FAIL conditions
- Escalation paths
- Artifact versioning
- Cost awareness

There is no forward-only mode.

---

# 2. Primary Loops

The system contains five core loops:

1. Narrative Loop
2. Validation Loop
3. Continuity Loop
4. Production Loop
5. Cost Loop

Each loop has entry, exit, and escalation rules.

---

# 3. Narrative Loop

Purpose: Ensure structural integrity before production.

Flow:

story-architect  
→ script-breakdown  
→ character-psychology  
→ narrative-red-team  
→ audience-simulator  

If FAIL:
→ revise structure  
→ increment version  
→ rerun validation  

Exit Condition:
- Structural PASS
- Stakes validated
- Characters coherent

No production work begins before this loop passes.

---

# 4. Validation Loop

Purpose: Ensure realism and credibility.

Flow:

research-agent  
→ plausibility-auditor  
→ cultural-check (if applicable)  

If FAIL:
→ revise scene  
→ update truth packet  
→ rerun plausibility  

Exit Condition:
- Plausibility score ≥ threshold
- No high-risk cultural inaccuracies
- No factual contradictions

Validation must PASS before world-state update.

---

# 5. Continuity Loop

Purpose: Maintain world coherence across scenes.

Flow:

world-state-tracker  
→ continuity-supervisor  

If FAIL:
→ revise scene  
→ regenerate state diff  
→ increment WORLD_STATE version  

Exit Condition:
- No contradictions
- No drift against locks
- Timeline coherent

Continuity loop runs after every validated scene.

---

# 6. Production Loop

Purpose: Convert validated scenes into stable outputs.

Flow:

shot-planner  
→ (optional) storyboard-generator  
→ prompt-packager  
→ generate  
→ qc-grader  

If QC = FIX:
→ minor prompt tweak  
→ regenerate  

If QC = FAIL:
→ regen-analyzer  
→ modify GenPack  
→ regenerate  

Exit Condition:
- QC PASS
- No lock violations
- Drift risk acceptable

This loop is the most cost-sensitive.

---

# 7. Cost Loop

Purpose: Prevent runaway spending.

Flow:

cost-optimizer  
→ budget-gates  
→ model-router  

If over budget:
→ simplify shot
→ downgrade tier
→ split shots
→ shorten duration

If regen limit exceeded:
→ enforce regen-analyzer
→ escalate or simplify

Exit Condition:
- Spend within cap
- Tier allocation rational
- Regen count controlled

Budget gates can override production loop.

---

# 8. Escalation Paths

Each loop may escalate to higher tier models.

Escalation hierarchy:

Tier 1 → Tier 2 → Tier 3  
or  
Throughput → Judgment → Vision  

Escalation allowed only when:
- Defined in skill
- Logged
- Cost impact evaluated
- Budget-gates approve

Escalation without documentation violates contract.

---

# 9. Cross-Loop Interactions

Loops are not isolated.

Examples:

- QC failure may trigger continuity check.
- Regen-analyzer may trigger shot simplification.
- Cost overrun may force narrative simplification.
- Plausibility issue may alter world-state assumptions.

All cross-loop triggers must produce versioned artifacts.

---

# 10. Global Hard Stops

The system halts if:

- Budget cap exceeded
- Lock violation unresolved
- World-state contradiction persists
- Artifact version overwritten
- Run-log missing entry

Hard stop requires human review.

---

# 11. Loop Discipline Rules

1. Never bypass upstream loop.
2. Never generate without locks.
3. Never escalate without routing.
4. Never regenerate blindly.
5. Never exceed regen limit without analyzer.
6. Never continue after FAIL without revision.

Loops exist to prevent entropy.

---

# 12. Visual Flow Summary

Narrative  
↓  
Validation  
↓  
Continuity  
↓  
Production  
↓  
QC  
↓  
(Regen Loop if needed)  
↓  
Cost Check  
↓  
Finalize  

At any FAIL:
→ loop backward  
→ version increment  
→ log run  

---

# 13. Philosophy

The system is designed to:

- Fail early
- Fail cheaply
- Fail visibly
- Improve iteratively
- Scale without memory collapse

Linear pipelines break at scale.

Looped systems endure.
