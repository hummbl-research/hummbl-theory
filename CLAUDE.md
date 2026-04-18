# CLAUDE.md — HUMMBL Theory Enhancement Project

This file governs Claude Code's behavior when working across the three HUMMBL theory repositories.

---

## Scope of This Project

This project spans three repositories (two existing, one to be initialized):

| Repo | Location | Status | Role |
|------|----------|--------|------|
| `hummbl-bibliography` | `PROJECTS/hummbl-bibliography/` | Live, v2.0.0 | Empirical evidence layer — 260 curated works across 13 tiers |
| `hummbl-tuples` | `PROJECTS/hummbl-tuples/` | Live, draft spec | Governance primitive layer — typed tuples for delegation/evidence |
| `hummbl-theory` | `PROJECTS/hummbl-theory/` | Initializing | Theoretical synthesis layer — MM, WM, BKI, Base120 integration |

The **theory project** is the integration surface. It does not replace the other two — it synthesizes and coordinates them.

---

## Foundational Distinctions (Hard Invariants)

These are load-bearing. Never blur them.

### Mental Models vs World Models

- **Mental models** = reasoning operators / interpretive lenses → Base120 IS this
- **World models** = stateful predictive representations of environments, actors, dynamics
- Base120 **operates on** world models; it is not a world model
- HUMMBL's strongest claim: "a governed mental-model layer for reasoning over partial world models"

See `MM.md` and `WM.md` in this directory for the full specification.

### VERUM (Append-Only Sovereignty, formerly Base4)

- The audit log is truth. Writing IS the act. The system never reads its own log.
- External tools analyze; the system does not self-observe its own output
- All governance tuples are append-only JSONL — no silent mutations

### BKI (Belonging as Knowledge Infrastructure)

- Belonging is a **structural precondition** for knowledge creation, not a soft outcome
- BKI explains why governance frameworks fail in deployment even when technically correct
- HUMMBL's platform IS the belonging infrastructure for AI governance adoption
- The four BKI propositions: Cognitive Scaffolding, Relational Validation, Embodied Knowing, Symbolic Systems
- The Broccolilly Equation: S × T × I × C × D = R

---

## Working Conventions

### Reading Before Writing

Before editing any theory document, read the current state. Theory documents are living — prior draft decisions matter.

### Evidence Standards

Every theoretical claim needs one of:
- A bibliography key (e.g., `Kahneman2011ThinkingFast`)
- A research note path (e.g., `hummbl-tuples/research_notes/2026-03-27-mental-models-vs-world-models.md`)
- An explicit `[HYPOTHESIS]` or `[ESTIMATE]` tag if unsourced

Unsourced claims are not acceptable in theory documents. Flag as `[UNVERIFIED]` if uncertain.

### Status Tags

All theoretical claims in this project carry one of:
- `[STATUS: LIVE]` — in production, empirically testable in current stack
- `[STATUS: DESIGNED]` — spec exists, not yet in production
- `[STATUS: PROPOSED]` — hypothesis, not yet designed or built
- `[STATUS: REJECTED]` — tried, failed, documented as negative result

Never present roadmap as reality.

### No Ollama on MBP

Local inference (consolidator, qwen3.5:9b) runs on nodezero (100.109.69.16:11434). Never invoke Ollama locally.

### Stdlib-Only

Any reference implementation or validation tooling in `hummbl-theory` uses Python stdlib only. No third-party runtime dependencies.

---

## Cross-Repo Coordination

### Bibliography → Theory

When theory documents reference empirical claims, they cite bibliography keys from `hummbl-bibliography/bibliography/T*.bib`. The bibliography is the evidence layer — theory cites it, does not duplicate it.

Query the bibliography:
```bash
cd PROJECTS/hummbl-bibliography/toolkit
node src/query.js --transformation SY
node src/query.js --nist-function GOVERN
```

### Tuples → Theory

The tuple taxonomy (`hummbl-tuples`) defines the governance primitive surface. Theory documents describe what tuples ARE for; tuples repo defines how they ARE.

When theory makes a claim about governance logging, check `hummbl-tuples/schemas/` for what fields are canonical.

### Theory → hummbl-dev

`hummbl-theory` produces publishable artifacts that feed into:
- `hummbl-governance` (product implementation)
- `hummbl-dev` (developer profile and positioning)
- Papers, essays, talks, standards proposals

Theory is upstream of implementation, not a description of it.

---

## Key Research Directions (as of Apr 2026)

1. **MM/WM formal interface** — typed contracts between the mental-model layer and world-model state
2. **Minimum viable operator set** — what subset of Base120 is sufficient for safe delegation?
3. **Tuple vocabulary for world-model state** — formal update, contradiction, and confidence primitives
4. **BKI × Base120 integration** — which operators are preconditioned on belonging-state?
5. **ARCANA → Base120 mapping** — 28 philosophical lenses partially mapped to bibliography; gap to operator families
6. **DREAM mode (HULE capture)** — `/dream` skill = human-level unstructured learning event; integration with HRSI framework

---

## Files in This Repository

| File | Purpose |
|------|---------|
| `CLAUDE.md` | This file — project governance for Claude |
| `MM.md` | Mental Models layer specification (living) |
| `WM.md` | World Models layer specification (living) |
| `BKI.md` | BKI theory integration (to be created after transcript review) |
| `ARCANA.md` | ARCANA × HUMMBL synthesis map (to be created) |
| `CLAIMS.md` | Candidate publishable claims with evidence and status tags |
| `GAPS.md` | Open research gaps and negative results |

---

## Prohibited Actions

- Do not blur MM and WM — they are architecturally distinct layers
- Do not present `[PROPOSED]` claims as `[LIVE]`
- Do not add third-party runtime dependencies to any reference implementation
- Do not commit directly to main in any hummbl-* repo — PR workflow only
- Do not modify `hummbl-bibliography/` validation logic without running `npm test` first
- Do not touch `hummbl-tuples/schemas/` without a matching ADR entry

---

## Canonical External References

- `.claude/rules/theoretical-foundations.md` — always-injected session context
- `PROJECTS/arcana/` — 28-lens philosophical framework; BKI docs for Claude AI
- `founder_mode/docs/research/` — research notes including world-model literature
- `_state/cognition/intent.md` — current session intent
