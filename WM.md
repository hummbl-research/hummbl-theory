# WM.md — World Models Layer

**Document type**: Living specification  
**Project**: HUMMBL Theory Enhancement  
**Status**: Initial draft — awaiting transcript enrichment  
**Last updated**: 2026-04-10

---

## What a World Model Is

A world model is a **stateful predictive representation** of environments, actors, dynamics, and their evolution over time. It represents *what is currently believed* about the world — not how to reason about it.

World models in HUMMBL are:
- **partial** — no complete ground truth; beliefs are maintained under uncertainty
- **governed** — updates are logged, attributable, and auditable
- **layered** — environment state, actor state, task state, and memory are distinct layers
- **operated on** by mental models (Base120), not identical to them

---

## World Model Layers in HUMMBL

| Layer | Contents | Primary update source |
|-------|----------|----------------------|
| **Environment state** | External signals, adapter outputs, system health | Briefing adapters (GitHub, Linear, Calendar, Security) |
| **Actor state** | Agent identities, trust levels, capabilities, constraints | IDP delegation tokens (DCT), guardrail files |
| **Task state** | Current intent, sprint goals, open work items | `_state/cognition/intent.md`, Linear issues |
| **Memory / retrieval** | Cognition ledger, bus history, past briefings | Open Brain (:11435), ledger.jsonl, BM25 index |
| **Predicted dynamics** | Projections, risk classifications, scenario models | Sprint recommender, cost projections |

---

## Architecture Position

```
MENTAL MODELS (Base120)
        │
        │ select and apply operators
        ▼
WORLD MODEL (partial, governed)
  ├── environment state   ← what's happening outside
  ├── actor state         ← who is in the system and what they can do
  ├── task state          ← what we're trying to accomplish right now
  ├── memory / retrieval  ← what we know from before
  └── predicted dynamics  ← what we expect to happen
        │
        │ produces observations
        ▼
TUPLES (CONTRACT · DCT · DCTX · SYSTEM · EVIDENCE)
        │
        │ append-only audit log
        ▼
GOVERNANCE BUS / COGNITION LEDGER
```

---

## HUMMBL's Positioning Claim

HUMMBL is a **governed mental-model layer for reasoning over partial world models**.

This is the strongest defensible claim. It avoids:
- **overstating**: claiming full world-model capability where only reasoning structure exists today
- **understating**: treating mental models as generic prompts rather than typed operator families acting over structured state

---

## What Counts as World-Model Infrastructure in the Current Stack

| Component | WM role |
|-----------|---------|
| `cognition/ledger.jsonl` | Long-term memory and belief persistence |
| `cognition/boot_context.py` | Loads prior beliefs into session context |
| `cognition/retriever.py` | Cross-pool belief retrieval (5 memory pools) |
| `_state/coordination/messages.tsv` | Actor-to-actor communication history |
| `_state/cognition/intent.md` | Current task state |
| Briefing adapters (7 live) | Real-time environment state updates |
| Open Brain (:11435) | Hub-and-spoke shared world state across agents |
| IDP (DCT, DCTX) | Governed actor state with delegation chains |

---

## Governed Update Protocol

World-model updates in HUMMBL are not silent mutations. The governing principle (Base4):

1. **Append-only** — beliefs accumulate; old beliefs are not overwritten silently
2. **Attributable** — every update records its source agent, timestamp, and evidence
3. **External analysis** — the system does not read its own update log for inference (post-mortem artifact, not live feedback)
4. **Tuple-wrapped** — significant state transitions emit EVIDENCE or SYSTEM tuples

---

## Open Research Questions

- [ ] What typed tuple vocabulary should govern world-model state updates? (see `hummbl-tuples` open question)
- [ ] How does HUMMBL handle contradictory world-model beliefs from different adapters?
- [ ] Can world-model confidence scores be formally defined and logged?
- [ ] At what layer does BKI belonging-state become a world-model input vs. a mental-model precondition?
- [ ] How does the consolidator (nightly, nodezero) formally update the world model vs. just summarizing memory?

---

## The MM/WM Distinction — Why It Matters for Claims

| Claim | Verdict |
|-------|---------|
| "HUMMBL has a world model" | **Overstated** — HUMMBL has world-model *infrastructure*, not a unified world model |
| "HUMMBL is only a prompting system" | **Understated** — Base120 is a typed operator library, not generic prompts |
| "HUMMBL has a governed mental-model layer for reasoning over partial world models" | **Correct** — defensible, differentiating, honest about current state |
| "Base120 IS the world model" | **Wrong** — Base120 operates ON world state; it does not represent world state |

---

## Canonical References

- `PROJECTS/hummbl-tuples/research_notes/2026-03-27-mental-models-vs-world-models.md` — foundational distinction
- `founder_mode/docs/research/R2_unified_world_models_bitter_lesson_2026.md` — world models in current AI literature
- `founder_mode/docs/research/ambient_intelligence_reconciliation_2026-03-20.md` — ambient intelligence positioning
- `PROJECTS/hummbl-tuples/docs/specs/REASONING_SEMANTICS.md` — reasoning semantics spec
- `.claude/rules/theoretical-foundations.md` — always-injected project context
