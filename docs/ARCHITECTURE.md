# Architecture

AI Video Production Skills is not a linear pipeline.

It is a gated, loop-driven, artifact-based production architecture.

This document explains how the system is structured.

---

# 1. High-Level Structure

The framework operates across five layers:

1. Narrative Layer
2. Validation Layer
3. Continuity Layer
4. Production Layer
5. Governance Layer

Each layer enforces constraints before allowing progression.

---

# 2. System Flow Overview

```mermaid
flowchart TD

A[Story Architect] --> B[Script Breakdown]

B --> C[Character / Set / Voice Locks]

C --> D[Research Agent]
D --> E[Plausibility Auditor]

E -->|Pass| F[World State Tracker]
E -->|Fail| A

F --> G[Shot Planner]
G --> H[Prompt Packager]

H --> I[Proxy Render]

I --> J[QC Grader]
J -->|Pass| K[Regen Analyzer]
J -->|Fail| H

K --> L[Cost Optimizer]
L -->|Within Budget| M[Final Render]
L -->|Over Budget| G

subgraph Governance
N[Model Router]
O[Budget Gates]
end

N -.controls.-> D
N -.controls.-> E
N -.controls.-> J

O -.enforces.-> I
O -.enforces.-> L
