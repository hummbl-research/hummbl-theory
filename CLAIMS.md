# CLAIMS.md — Publishable Claims with Evidence and Status

**Purpose**: Every claim HUMMBL makes in papers, pitches, or product positioning is listed here with its evidence chain and status tag. This is the single source of truth for "what can we say and how strongly."

**Status tags**:
- `[LIVE]` — implemented, tested, in production
- `[DESIGNED]` — spec exists, not yet in production
- `[PROPOSED]` — hypothesis with theoretical warrant, not yet built or tested
- `[VERIFIED]` — claim has been empirically tested or peer-reviewed
- `[REJECTED]` — tried, failed, documented as negative result

---

## Tier 1: Theorem-Grade Claims

These follow from mathematical results. They are not opinions.

### C1: Governance must scale with AI capability
**Claim**: As AI system variety V(AI) increases, governance variety V(G) must increase proportionally. Static governance frameworks violate Ashby's Law of Requisite Variety.
**Evidence**: Ashby (1956), Conant & Ashby (1970). Proof sketch in `papers/ashby-proof/`.
**Status**: `[PROPOSED]` — mathematical argument complete; not yet empirically validated against real governance deployments.
**Papers**: Ashby Proof Sketch, Sovereign Agents (scaffold)

### C2: Governance infrastructure must model the governed system
**Claim**: Any maximally successful governance system must contain an isomorphic model of the AI systems it governs (the World Model layer).
**Evidence**: Conant & Ashby Good Regulator Theorem (1970).
**Status**: `[DESIGNED]` — WM layer specified in `WM.md`; partially implemented via briefing adapters.
**Papers**: Ashby Proof Sketch, Governance Tuple

### C3: No single governance framework can be complete
**Claim**: Any governance framework formal enough to specify all permissible AI behaviors will contain legitimate behaviors it cannot classify. Pluralism is a logical necessity, not a preference.
**Evidence**: Gödel (1931), Second Incompleteness Theorem.
**Status**: `[PROPOSED]` — theoretical warrant only; no empirical test designed.
**Papers**: Friston-BKI (§1)

---

## Tier 2: Empirically Warranted Claims

These are supported by research from other domains, applied to AI governance by analogy. The analogy is defended but not yet independently validated.

### C4: Multi-model governance outperforms single-framework governance
**Claim**: A library of governance mental models (Base120) outperforms reliance on a single framework (e.g., "just use NIST") in uncertain, rapidly evolving AI environments.
**Evidence**: Tetlock (2005) — foxes (multi-model) outperform hedgehogs (single-model) in prediction accuracy. Gigerenzer (1999) — simple heuristic libraries outperform optimization.
**Status**: `[PROPOSED]` — empirical warrant from adjacent domain; not yet tested in AI governance specifically.
**Papers**: Base120 Formal Draft, Corpus XVI.1–XVI.2

### C5: AI systems mathematically marginalize under-represented communities
**Claim**: Free energy minimization over biased training distributions produces systematic suppression of minority observations. This is a mathematical consequence, not an intent.
**Evidence**: Friston (2006/2010) — free energy principle. Barabási & Albert (1999) — preferential attachment. Bender et al. (2021) — empirical corroboration.
**Status**: `[PROPOSED]` — formal model in `papers/friston-bki/`; not yet empirically validated with real distribution data.
**Papers**: Friston-BKI, BKI White Paper (scaffold)

### C6: Belonging is a structural precondition for governance adoption
**Claim**: Governance content delivered into low-belonging environments produces compliance theater, not behavioral change. Belonging infrastructure must precede content delivery.
**Evidence**: BKI 4 propositions. Dweck (2006) — growth mindset as adoption precondition. Vygotsky (1934) — ZPD requires scaffolding. Ubuntu (Ramose 1999) — knowledge is socially constituted.
**Status**: `[PROPOSED]` — theoretical synthesis; BKI propositions not yet empirically tested as a unit.
**Papers**: BKI Governance Draft, Friston-BKI, BKI White Paper (scaffold)

### C7: Certification resolves the AI governance lemons problem
**Claim**: Without trusted certification, the AI governance market collapses via adverse selection — genuine governance is indistinguishable from checkbox compliance.
**Evidence**: Akerlof (1970) — market for lemons. Applied to AI governance certification.
**Status**: `[PROPOSED]` — theoretical warrant; HUMMBL-certified adapter program not yet launched.
**Papers**: Corpus XVII.1

---

## Tier 3: Implementation Claims

These describe what HUMMBL has actually built and shipped.

### C8: Append-only audit trails provide tamper-evident governance proof
**Claim**: HUMMBL's VERUM-aligned audit log (append-only JSONL, SHA-256 hashing) provides tamper-evident proof that governance happened.
**Evidence**: Lamport (1978) — logical clocks for causal ordering. Merkle (1979) — hash trees for integrity verification. Implemented in `hummbl-governance` PyPI package.
**Status**: `[LIVE]` — `AuditLog`, `LamportClock`, EAL conformance suite with 37 tests.
**Papers**: VERUM Draft, Coordination Bus Draft, Governance Tuple

### C9: Four kill switch modes are sufficient for graduated AI safety response
**Claim**: DISENGAGED → HALT_NONCRITICAL → HALT_ALL → EMERGENCY covers the practical safety response space.
**Evidence**: Implemented and tested in `hummbl-governance.KillSwitch`. 583+ tests total.
**Status**: `[LIVE]` — shipped in `hummbl-governance` v0.3.0 on PyPI.
**Papers**: Kill Switch Formal Draft

### C10: Zero third-party runtime dependencies are achievable for governance primitives
**Claim**: All core governance primitives (kill switch, circuit breaker, cost governor, delegation tokens, audit log, bus writer, schema validator, EAL) can be implemented with Python stdlib only.
**Evidence**: `hummbl-governance` package — 21 modules, 0 runtime dependencies, 583 tests.
**Status**: `[LIVE]` — shipped on PyPI.
**Papers**: Governance Tuple, Coordination Bus

### C11: HUMMBL implements all 8 Ostrom commons governance principles
**Claim**: HUMMBL's architecture maps to all 8 of Ostrom's design principles for sustainable commons governance. Competitors typically cover 2/8.
**Evidence**: Mapping table in `papers/ostrom-mapping/`. Each principle mapped to specific HUMMBL primitive.
**Status**: `[DESIGNED]` — mapping is analytical; "competitors cover 2/8" claim needs systematic competitor audit.
**Papers**: Ostrom Mapping, Corpus XIV.4

---

## Claims Pending Development

| ID | Claim | Blocker |
|----|-------|---------|
| C12 | Base120 operators form a complete set in Klein's sense | Needs formal completeness proof or conjecture |
| C13 | Delegation depth has a formal safety bound | Needs proof in Delegation Depth paper |
| C14 | Depth laundering is exploitable in current multi-agent systems | Needs demonstration on real system |
| C15 | HUMMBL governance reduces transaction costs (North) | Needs empirical measurement with real enterprise |
