# GAPS.md — Open Research Gaps and Negative Results

**Purpose**: Intellectual honesty file. Every known gap, unresolved question, and negative result is tracked here. A gap is not a weakness — it is a research direction.

---

## Category 1: Mathematical Gaps

### G1: Base120 Completeness
**Question**: Do the 6 Base120 operators (P, IN, CO, DE, RE, SY) form a complete set in Klein's sense? Can every cognitive transformation be expressed as a composition of these 6?
**Why it matters**: If incomplete, there exist governance-relevant reasoning patterns that Base120 cannot express. If complete, Base120 has a strong universality claim.
**What we know**: The operators were designed by domain analysis, not by completeness proof. The 59-entry corpus maps to all 6 families, but coverage is not proof.
**Open questions from `lineages/transformation-theory.md`**:
- Do the 6 operators form a group (invertible), monoid (identity), or semigroup?
- Which operator sequences are canonically reversible (adjoint pairs)?
- Is there a cognitive transformation that requires an operator outside {P, IN, CO, DE, RE, SY}?
**Difficulty**: Hard. This is a research paper on its own.

### G2: Variety Calculation Precision
**Question**: The Ashby proof sketch calculates HUMMBL's variety as ≥10.5M states (~23.3 bits). But V(AI) for a frontier LLM is astronomical. Is the governance gap actually widening despite HUMMBL's variety?
**Why it matters**: If V(AI) >> V(G) even with HUMMBL, the Ashby argument proves the problem but not that HUMMBL solves it.
**What we know**: Attenuation mechanisms V(D) — scope boundaries, delegation limits, cost caps — reduce the effective variety that governance must match. The question is whether V(D) grows fast enough.
**Difficulty**: Medium. Requires formalizing V(D) for HUMMBL's specific architecture.

### G3: Delegation Depth Safety Bound
**Question**: What is the maximum safe delegation chain length in multi-agent systems? Is there a formal bound, or is it environment-dependent?
**Why it matters**: Depth Laundering paper claims unbounded delegation is exploitable. The constructive question is: what bound is safe?
**What we know**: Draft exists (294L). The bound likely depends on trust decay rate per hop.
**Difficulty**: Medium.

---

## Category 2: Empirical Gaps

### G4: BKI Propositions — No Empirical Test
**Question**: Do the 4 BKI propositions (Cognitive Scaffolding, Relational Validation, Embodied Knowing, Symbolic Systems) hold empirically in AI governance adoption contexts?
**Why it matters**: BKI is currently a theoretical framework. Without empirical validation, it's a hypothesis, not a result.
**What we know**: Each proposition has theoretical warrant from multiple independent traditions (Friston, Vygotsky, Ubuntu, Peirce). No controlled study has tested them as a unit.
**Path to closing**: Design a field study with alpha testers (Travis, Dan, Jenna, Donald). Measure governance adoption behavior under high-belonging vs. low-belonging conditions.
**Difficulty**: Hard. Requires real users and controlled conditions.

### G5: Tetlock Analogy — Not Validated for AI Governance
**Question**: Does the fox/hedgehog advantage (Tetlock 2005) transfer from geopolitical prediction to AI governance? Multi-model reasoning may not outperform single-framework compliance in regulated environments where regulators demand a specific framework.
**Why it matters**: If regulators mandate NIST AI RMF, having 120 models doesn't help — you need the one they require.
**What we know**: The Tetlock analogy is strong in principle but unvalidated in the specific domain. Enterprise compliance may reward hedgehog behavior (pick one framework, do it perfectly).
**Path to closing**: Interview enterprise governance buyers. Do they want flexibility or conformity?
**Difficulty**: Low-medium. Interview study, not experiment.

### G6: Free Energy Suppression — No Distribution Data
**Question**: Does Friston-BKI's Suppression Inequality hold on real training distributions? The formal model predicts marginalization, but the effect size is unknown.
**Why it matters**: If the suppression effect is negligible in practice, the BKI argument loses its strongest formal leg.
**What we know**: Bender et al. (2021) provides qualitative corroboration. Quantitative measurement requires access to training distribution statistics that model providers don't publish.
**Path to closing**: Use proxy data (Common Crawl language distribution, Wikipedia coverage by language/topic) to estimate π_A/π_B ratios and predicted suppression.
**Difficulty**: Medium.

---

## Category 3: Architectural Gaps

### G7: World Model Layer — Not Implemented
**Question**: HUMMBL's architecture requires a World Model layer (Conant-Ashby). The briefing adapters provide fragments of world state, but there is no unified WM representation.
**Why it matters**: Without WM, HUMMBL violates its own Good Regulator Theorem claim (C2).
**What we know**: `WM.md` specifies 5 layers (environment, actor, task, memory, dynamics). The briefing system partially implements environment + actor state. No formal WM integration exists.
**Path to closing**: Design a unified WM schema that ingests adapter outputs into a queryable state representation.
**Difficulty**: Medium-hard. Architecture + implementation.

### G8: MM/WM Interface — Not Formalized
**Question**: How does a Base120 mental model operator interact with world model state? What is the typed interface between MM and WM?
**Why it matters**: This is HUMMBL's core architectural distinction. If the interface is informal, the distinction is hand-waving.
**What we know**: `MM.md` and `WM.md` describe the layers. No formal interface contract exists. The tuple schema (`hummbl-tuples`) provides a candidate structure.
**Path to closing**: Define a typed protocol: `MM_Operator × WM_State → (WM_State', GovernanceTuple)`.
**Difficulty**: Medium. Mostly design work.

### G9: P-Family Underspecification
**Question**: The P (Perspective/Identity) family has the least formal treatment of any Base120 family. What distinguishes a P-operator from a prompt instruction?
**Why it matters**: If P-operators are just "think about this from X's perspective," they're prompts, not operators.
**What we know**: Goffman (1974) and Lakoff & Johnson (1980) provide theoretical grounding (Corpus XV). But no formal distinction between a P-operator and a well-crafted prompt has been articulated.
**Path to closing**: Define P-operators as frame-selection functions that constrain the hypothesis space before reasoning begins, not during.
**Difficulty**: Medium.

---

## Category 4: Market/Positioning Gaps

### G10: Competitor Governance Variety — Not Measured
**Question**: The Ostrom mapping claims competitors cover 2/8 principles. Which competitors? What exactly do they cover?
**Why it matters**: "2/8" without named competitors is an unsourced claim.
**Path to closing**: Systematic competitor audit (AGT, JetStream, Credo, Zenity) against Ostrom's 8 principles.
**Difficulty**: Low. Desk research.

### G11: Transaction Cost Reduction — Not Measured
**Question**: Does HUMMBL actually reduce governance transaction costs (North 1990)?
**Why it matters**: This is the core commercial claim — governance with HUMMBL is cheaper than governance without it.
**Path to closing**: Measure time-to-compliance for an enterprise with and without HUMMBL. Requires a real client engagement.
**Difficulty**: Hard. Requires paying customer.

---

## Negative Results

### N1: Compliance Theater Is Not Always Wrong
**Observation**: The Compliance Theater paper (204L) argues checklists always fail. But in regulated industries (healthcare, finance), checklist compliance IS the legal requirement. A company that passes the checklist audit is legally compliant even if behaviorally unchanged.
**Implication**: BKI's argument against compliance theater needs to be nuanced — it's not that checklists are useless, it's that they're insufficient for behavioral change. Legal compliance and governance effectiveness are different claims.
**Status**: Incorporated as nuance in BKI Governance Draft.

### N2: Ubuntu Universality Limit
**Observation**: Ubuntu philosophy is powerful as a BKI foundation, but it originates from a specific cultural tradition (Southern African). Claiming it as a universal epistemological principle risks the same hegemonic move BKI criticizes.
**Implication**: BKI should present Ubuntu as one of several convergent traditions (alongside Peirce, Hutchins, Vygotsky) that independently arrive at relational epistemology — not as THE foundation.
**Status**: Addressed in corpus structure (Ubuntu is XII.3, not I.1).
