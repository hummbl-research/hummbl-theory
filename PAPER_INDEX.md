# Paper Index

Complete inventory of HUMMBL research papers, their locations, and status.

**Last updated**: 2026-04-18
**Total papers**: 24 (22 drafts + 2 scaffolds)
**Published**: 0
**On arXiv**: 0

---

## Papers in hummbl-theory

| Paper | Directory | Lines | Status |
|-------|-----------|-------|--------|
| Ashby Requisite Variety Proof Sketch | `papers/ashby-proof/` | ~166 | Draft |
| Ostrom Commons Governance Mapping | `papers/ostrom-mapping/` | ~150 | Draft (sales artifact) |
| Free Energy Suppression as Epistemic Violence | `papers/friston-bki/` | ~180 | Draft |
| BKI White Paper | `papers/bki-white-paper/` | scaffold | Pre-draft |
| Sovereign Agents | `papers/sovereign-agents/` | scaffold | Pre-draft |

## Papers in founder_mode/docs/publications/

### With LaTeX versions

| Paper | File | Lines | LaTeX |
|-------|------|-------|-------|
| CRAI 2026 Typed Tuple Profile | `CRAI_2026_TYPED_TUPLE_PROFILE_DRAFT.md` | 373 | `.tex` (555L) |
| Governance Tuple: Atomic Record | `TUPLE_ATOMIC_RECORD_DRAFT.md` | 735 | `.tex` (711L) |

### Markdown only

| Paper | File | Lines |
|-------|------|-------|
| Governance Receipts: Human-Readable Audit | `HCI_GOVERNANCE_RECEIPTS_DRAFT.md` | 746 |
| Coordination Bus: Append-Only Multi-Agent | `COORDINATION_BUS_DRAFT.md` | 576 |
| Depth Laundering | `DEPTH_LAUNDERING_DRAFT.md` | 530 |
| Identity Recovery in Agentic AI | `AGENTIC_IDENTITY_RECOVERY_DRAFT.md` | 524 |
| Framework Crosswalk: NIST/EU/ISO/OWASP | `FRAMEWORK_CROSSWALK_DRAFT.md` | 467 |
| Kill Switch: Formal Safety State Machine | `KILL_SWITCH_FORMAL_DRAFT.md` | 414 |
| BKI Governance: Belonging as Prerequisite | `BKI_GOVERNANCE_DRAFT.md` | 358 |
| Base120: Pre-Hoc Operator Commitment | `BASE120_FORMAL_DRAFT.md` | 355 |
| Phantom Authority: LLM Authorization Threats | `PHANTOM_AUTHORITY_DRAFT.md` | 338 |
| Agentic Identity Failures Taxonomy | `AGENTIC_IDENTITY_DRAFT.md` | 336 |
| Benchmark Decay and the Goodhart Trap | `BENCHMARK_DECAY_DRAFT.md` | 326 |
| Token Budget Governance | `TOKEN_BUDGET_GOVERNANCE_DRAFT.md` | 315 |
| Delegation Depth: Formal Authority Bounds | `DELEGATION_DEPTH_DRAFT.md` | 294 |
| VERUM: Append-Only Governance Sovereignty | `VERUM_GOVERNANCE_DRAFT.md` | 269 |
| TRACE: Probe-Class Evaluation Harness | `TRACE_EVALUATION_DRAFT.md` | 250 |
| Ashby Governance (original) | `ASHBY_GOVERNANCE_DRAFT.md` | 211 |
| Compliance Theater | `COMPLIANCE_THEATER_DRAFT.md` | 204 |

### Non-academic

| Document | File | Lines | Type |
|----------|------|-------|------|
| NCCoE Public Comment (NIST Agent Identity) | `NCCOE_CONCEPT_PAPER_DRAFT_2026-03-11.md` | 299 | Policy submission |

---

## Consolidation Plan

| Action | Source | Target | Rationale |
|--------|--------|--------|-----------|
| Merge | Ashby Governance (211L) | Ashby Proof Sketch (166L) | Proof sketch is sharper; absorb any unique content from original |
| Merge | BKI Governance (358L) | Friston-BKI (180L) | Friston version has formal core; absorb empirical framing from original |
| Pair | Phantom Authority (338L) | Depth Laundering (530L) | Natural companion pair — threat model + exploit |
| Retire | Compliance Theater (204L) | Fold into BKI Governance/Friston-BKI | The argument is made better in the BKI framing |
| Repurpose | NCCoE Comment (299L) | Blog post or next NIST comment period | Deadline passed |

---

## Wave 1 arXiv Targets

| Paper | arXiv Category | Pre-submission blocker |
|-------|---------------|----------------------|
| Friston-BKI | cs.CY | Related work section, notation consistency |
| Depth Laundering | cs.CR | Evaluation section (demonstrate exploit) |
| Governance Tuple | cs.AI | LaTeX formatting pass, abstract polish |

---

## Cross-references

- **Claims**: Every paper's claims are tracked in `CLAIMS.md`
- **Gaps**: Every paper's open questions are tracked in `GAPS.md`
- **Corpus**: Theoretical foundations in `foundations/corpus-v2-lateral-expansion.md`
- **Roadmap**: Publication timeline in `ROADMAP.md`
- **Checklist**: Pre-submission requirements in `SUBMISSION_CHECKLIST.md`
