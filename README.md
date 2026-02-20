# AI Video Production Skills

## Manifesto

AI can generate scenes.

It cannot maintain a world.

It cannot enforce continuity.  
It cannot protect character psychology.  
It cannot defend against plot holes.  
It cannot manage cost.  
It cannot scale without structure.

Narrative production is not prompting.  
It is constraint management.

This framework exists because:

- Memory must be externalized.
- Quality must be gated.
- Costs must be bounded.
- Models must be interchangeable.
- Systems must survive scale.

If your workflow breaks at 30 scenes, it is not production-ready.

This repository is an attempt to make AI storytelling disciplined, composable, and durable.

---

## What This Is

AI Video Production Skills is a model-agnostic, production-grade framework for building AI-assisted films and series.

It provides:

- Character / Set / Voice anti-drift systems
- Truth validation with citation requirements
- Plausibility scoring frameworks
- World-state continuity tracking
- Narrative red-teaming
- Audience simulation personas
- Structured shot planning
- Prompt packaging standards
- QC grading systems
- Regen learning loops
- Cost routing and budget gates
- Tiered model escalation policies

This is not a prompt collection.

It is infrastructure.

---

## Why This Exists

Most AI storytelling systems fail for predictable reasons:

- Characters drift visually and psychologically.
- Continuity collapses across scenes.
- Stakes feel artificial.
- Research is shallow or incorrect.
- Regeneration loops spiral out of control.
- Costs escalate without guardrails.
- Prompts grow longer instead of systems growing stronger.

This framework addresses those failures directly.

---

## Core Design Principles

1. Artifact-Based Memory  
   No reliance on chat history. All continuity is externalized.

2. Gate Enforcement  
   Nothing progresses without passing validation checks.

3. Loop Architecture  
   The system is closed-loop, not linear.

4. Model-Agnostic Routing  
   Works with Claude, GPT, Gemini, MiniMax, Qwen, or any future model.

5. Cost Awareness  
   Budget gates prevent silent overspend.

6. Composability  
   Skills operate independently and integrate cleanly.

---

## System Architecture

Narrative production is structured across five layers:

1. Narrative Layer  
   Story structure, character arcs.

2. Validation Layer  
   Research, plausibility, red-team, audience simulation.

3. Continuity Layer  
   Character locks, set locks, world state tracking.

4. Production Layer  
   Shot planning, prompt packaging, proxy rendering, QC, regen learning.

5. Governance Layer  
   Model routing and budget enforcement.

See `ARCHITECTURE.md` for full diagram.

---

## Closed-Loop Workflow

Story
↓
Research → Plausibility → Continuity
↓
Locks
↓
Shot Plan
↓
GenPack
↓
Proxy Render
↓
QC
↓
Regen Learning
↓
Cost Optimization


Failure at any stage loops backward.

There is no forward-only mode.

---

## Model Tiering

This framework separates intelligence into tiers:

Throughput Tier  
- Formatting  
- Extraction  
- Structured generation  

Judgment Tier  
- Red-team  
- Arbitration  
- High-impact rewrites  

Research Tier  
- Citation-heavy synthesis  

Vision Tier  
- Visual continuity validation  

Always use the cheapest viable tier.  
Escalate only when gates fail.

---

## Included Skills

Core skills include:

- story-architect  
- script-breakdown  
- character-lock  
- set-lock  
- voice-lock  
- research-agent  
- plausibility-auditor  
- character-psychology  
- narrative-red-team  
- audience-simulator  
- world-state-tracker  
- shot-planner  
- prompt-packager  
- qc-grader  
- regen-analyzer  
- cost-optimizer  
- model-router  
- budget-gates  

Each skill defines:

- Inputs  
- Outputs  
- Pass / fail gates  
- Escalation policy  
- Versioned artifacts  

---

## Example Project Included

See:
examples/demo_short_film/


The demo includes:

- Versioned locks  
- Truth packet  
- Plausibility audit  
- World state + state diff  
- Shot list  
- GenPack  
- QC report  
- Regen rules  
- Cost report  

This example proves the system structure works.

---

## Designed For Scale

This framework assumes:

- 50+ scenes
- Hundreds of shots
- Multi-model routing
- Iterative QC loops
- Budget ceilings
- Long-running pipelines

If a system cannot scale without collapsing continuity, it is not production-ready.

---

## What This Is Not

- Not a screenplay template
- Not a one-click generator
- Not a vendor-locked pipeline
- Not a collection of “magic prompts”

This is production infrastructure.

---

## Getting Started

1. Read `ARCHITECTURE.md`
2. Review `docs/loop_architecture.md`
3. Choose a data spine from `docs/data_spine_templates.md`
4. Start with:

   story-architect  
   script-breakdown  
   character-lock  
   set-lock  
   voice-lock  
   research-agent  
   plausibility-auditor  

5. Only then proceed to generation.

---

## Roadmap

- CLI orchestration starter
- Reference Google Sheets template
- Vision-based continuity validation
- Dialogue drift detection
- Editing heuristic skill
- Cost dashboard UI example
- Expanded example project

---

## Contributing

See `CONTRIBUTING.md`.

Contributions must:

- Define gates
- Define artifacts
- Remain model-agnostic
- Preserve loop integrity
- Strengthen system discipline

---

## License

MIT
