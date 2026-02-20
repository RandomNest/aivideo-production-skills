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
- Full execution logging  

This is not a prompt collection.

It is infrastructure.

---

## 🚀 Start Here

Before generating anything, read:

👉 **docs/how_to_run.md**

That guide defines:

- Project structure
- Execution order
- Gate enforcement
- Loop behavior
- Lock discipline
- Budget controls
- Logging requirements
- Proxy → final escalation policy

Do not begin generation before reading it.

---

## Core Design Principles

### 1. Artifact-Based Memory  
No reliance on chat history. All continuity is externalized.

### 2. Gate Enforcement  
Nothing progresses without passing validation checks.

### 3. Loop Architecture  
The system is closed-loop, not linear.

### 4. Model-Agnostic Routing  
Works with Claude, GPT, Gemini, MiniMax, Qwen, or any future model.

### 5. Cost Awareness  
Budget gates prevent silent overspend.

### 6. Composability  
Skills operate independently and integrate cleanly.

---

## Artifact Discipline

Everything is versioned.

- No artifact is overwritten.  
- Logs are append-only.  
- World-state updates require diffs.  
- Lock updates require version increments.  
- Generation must reference explicit artifacts.  

If it is not in a versioned artifact, it does not exist.

---

## System Architecture

Narrative production is structured across six layers:

1. **Narrative Layer**  
   Story structure, character arcs.

2. **Validation Layer**  
   Research, plausibility, red-team, audience simulation.

3. **Continuity Layer**  
   Character locks, set locks, voice locks, world-state tracking.

4. **Production Layer**  
   Shot planning, prompt packaging, proxy rendering, QC, regen learning.

5. **Governance Layer**  
   Model routing and budget enforcement.

6. **Observability Layer**  
   Run logging, cost tracking, regen tracking, audit history.

See `docs/ARCHITECTURE.md` for full system diagram.

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

See `docs/loop_architecture.md`.

---

## Model Tiering

This framework separates intelligence into tiers:

**Throughput Tier**  
- Formatting  
- Extraction  
- Structured generation  

**Judgment Tier**  
- Red-team  
- Arbitration  
- Psychological validation  

**Research Tier**  
- Citation-heavy synthesis  

**Vision Tier**  
- Visual continuity validation  
- Spatial reasoning  

Always use the cheapest viable tier.  
Escalate only when gates fail.

See `docs/model_policy.md`.

---

## Included Skills

### Narrative
- story-architect  
- script-breakdown  
- character-psychology  
- dialogue-consistency-check  

### Validation
- research-agent  
- plausibility-auditor  
- cultural-check  
- narrative-red-team  
- audience-simulator  

### Continuity
- character-lock  
- set-lock  
- voice-lock  
- world-state-tracker  
- continuity-supervisor  

### Production
- shot-planner  
- prompt-packager  
- storyboard-generator  
- qc-grader  
- regen-analyzer  

### Governance
- cost-optimizer  
- model-router  
- budget-gates  

### Observability
- run-logger  

Each skill defines:

- Required inputs  
- Required artifacts  
- Pass / fail gates  
- Escalation policy  
- Loop integration  
- Logging requirements  

---

## Example Project Included

See:

`examples/demo_short_film/`

The demo includes:

- Versioned locks  
- Truth packet  
- Plausibility audit  
- World state + state diffs  
- Shot list  
- GenPack  
- QC report  
- Regen rules  
- Cost report  
- Run logs  

The example proves the system structure works end-to-end.

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

1. Read `docs/how_to_run.md` (mandatory)  
2. Review `docs/ARCHITECTURE.md`  
3. Review `docs/loop_architecture.md`  
4. Choose a data spine from `docs/data_spine_templates.md`  
5. Initialize locks and world-state  
6. Only then begin generation  

Do not generate scenes before locks and validation loops are established.

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
- Respect budget policy  
- Respect model policy  
- Strengthen system discipline  

---

## License

MIT
