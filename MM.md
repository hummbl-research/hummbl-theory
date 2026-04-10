# MM.md — Mental Models Layer

**Document type**: Living specification  
**Project**: HUMMBL Theory Enhancement  
**Status**: Initial draft — awaiting transcript enrichment  
**Last updated**: 2026-04-10

---

## What Mental Models Are (and Are Not)

Mental models in HUMMBL are **reasoning operators** — structured interpretive lenses that determine *how* a system thinks, not *what* it thinks about.

They are NOT:
- prompts (those are delivery vehicles, not operators)
- world models (those represent current beliefs about state)
- general heuristics (these have typed families and composable structure)
- metaphors (they have testable predictions and governance footprints)

---

## The Base120 Operator Library

Base120 is the primary mental-model system. 120 operators organized across 6 cognitive transformation families:

| Family | Code | Core function |
|--------|------|---------------|
| Perspective / Identity | **P** | Frame and name what is. Anchor or shift point of view. |
| Inversion | **IN** | Reverse assumptions. Examine opposites, edges, negations. |
| Composition | **CO** | Combine parts into coherent wholes. |
| Decomposition | **DE** | Break complex systems into constituent parts. |
| Recursion | **RE** | Apply operations iteratively; outputs become inputs. |
| Meta-Systems | **SY** | Understand systems of systems; coordination and emergence. |

Each operator within a family is individually typed and addressable. The library is not a flat list — it is a structured vocabulary for deliberate reasoning.

---

## Architecture Position

```
┌─────────────────────────────────┐
│         TASK / INTENT           │  ← what we're trying to do
└─────────────────┬───────────────┘
                  │
┌─────────────────▼───────────────┐
│     MENTAL MODELS (Base120)     │  ← CHOOSE HOW to reason
│   P / IN / CO / DE / RE / SY   │
└─────────────────┬───────────────┘
                  │ operates on
┌─────────────────▼───────────────┐
│        WORLD MODEL              │  ← represents WHAT IS believed
│  environment · actors · state   │
└─────────────────────────────────┘
                  │ produces
┌─────────────────▼───────────────┐
│           TUPLES                │  ← records WHO chose WHAT path
│  CONTRACT · DCT · EVIDENCE      │  ← under WHAT control regime
└─────────────────────────────────┘
```

Base120 operates ON the world model. It is not the world model.

---

## Governing Properties

1. **Selectivity** — not all 120 operators activate for every task. Selection is governed by task type, epistemic stance, and control regime.

2. **Composability** — operators combine. P → DE is a valid path (name the frame, then decompose inside it). RE applied to CO is a valid recursive composition.

3. **Auditability** — which operators were selected is recorded in tuples. Reasoning paths are not opaque.

4. **Non-recursiveness** — the mental-model layer does not read its own audit log (Base4 principle). External analysis tools inspect the trace.

---

## Current Research Gaps

- [ ] Formal typed interfaces between operator families (what does CO → RE actually pass?)
- [ ] Minimum viable operator set for safe agent delegation (is 120 too many? what's the kernel?)
- [ ] Operator selection governance (how does a governed system choose which model to apply?)
- [ ] BKI integration: which operators are preconditioned on belonging-state? (P and SY are candidates)
- [ ] ARCANA alignment: 28 philosophical lenses mapped to bibliography, but not yet formally mapped to Base120 operators

---

## Canonical References

- `PROJECTS/hummbl-tuples/research_notes/2026-03-27-mental-models-vs-world-models.md` — foundational MM/WM distinction
- `PROJECTS/hummbl-bibliography/` — 240+ works tagged with HUMMBL transformation codes
- `PROJECTS/hummbl-bibliography/mappings/arcana_citations.json` — ARCANA lens → bibliography mapping
- `.claude/rules/theoretical-foundations.md` — always-injected project context
