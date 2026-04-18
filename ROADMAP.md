# HUMMBL Research Roadmap

**Author**: Reuben Bowlby, HUMMBL LLC
**Last updated**: 2026-04-18
**Status**: Active

---

## Mission

Establish HUMMBL as a recognized source of rigorous, cited research in AI governance — operating as a solo research lab with multi-agent production infrastructure, publishing under HUMMBL LLC.

## Current State (April 2026)

- **24 papers drafted**, 0 published
- **59-entry theoretical corpus** across 19 domain clusters, all citations verified
- **Open-source package** (`hummbl-governance` v0.3.0 on PyPI, 583 tests, 21 modules)
- **3 theoretical frameworks**: Base120 (mental models), VERUM (append-only sovereignty), BKI (belonging as knowledge infrastructure)
- **Multi-agent research pipeline**: parallel draft production, automated citation verification, corpus management

---

## Phase 1: First Publications (Apr–Jun 2026)

**Goal**: 3 papers on arXiv. Semantic Scholar author profile live.

### Wave 1 — arXiv submissions (target: May 2026)

| Priority | Paper | Lines | Target | Status | Action needed |
|----------|-------|-------|--------|--------|---------------|
| 1 | **Free Energy Suppression as Epistemic Violence** (Friston-BKI) | ~180 | arXiv cs.CY | Draft | Related work section, notation consistency check, abstract tighten |
| 2 | **Depth Laundering: Exploiting Unbounded Delegation** | 530 | arXiv cs.CR | Draft | Evaluation section (demonstrate exploit on hummbl-governance testbed), related work |
| 3 | **The Governance Tuple: Atomic Record for Auditable AI** | 735 + LaTeX | arXiv cs.AI | Draft | LaTeX formatting pass, abstract polish, cite hummbl-governance PyPI |

### Wave 1 support tasks

- [ ] Create Semantic Scholar author profile after first arXiv paper lands
- [ ] Set up ORCID for Reuben Bowlby
- [ ] Add `papers/` rendering to hummbl.io (each paper gets a landing page)
- [ ] Configure `/daily-research` to monitor Semantic Scholar for citations of our arXiv IDs

### Blog artifacts (publish on hummbl.io alongside arXiv)

- [ ] Ashby proof sketch → blog post: "Why AI Governance Must Scale: A Mathematical Proof"
- [ ] Ostrom mapping → blog post: "8 Principles for AI Commons Governance"
- [ ] Compliance Theater → blog post: "Why Checklists Fail at AI Governance"

---

## Phase 2: Conference Submissions (Jun–Sep 2026)

**Goal**: 2 papers submitted to peer-reviewed venues. 1 workshop acceptance.

### Primary targets

| Paper | Venue | Deadline (est.) | Fit |
|-------|-------|-----------------|-----|
| **Governance Receipts** (746L) | CHI 2027 | ~Sep 2026 | HCI + governance design. Strongest empirical paper — real system, real users. |
| **Kill Switch: Formal Safety State Machine** (414L) | SafeAI @ AAAI 2027 | ~Oct 2026 | Formal methods + safety. Clean state machine proofs. |
| **Framework Crosswalk** (467L) | IEEE AI Governance Workshop | ~Jul 2026 | Practitioner-oriented. Maps NIST/EU/ISO/OWASP to agentic primitives. |

### Workshop targets (lower bar, higher signal)

| Workshop | Conference | Why |
|----------|-----------|-----|
| MATS (Multi-Agent Trust and Safety) | AAMAS 2027 | Delegation depth, phantom authority, coordination bus |
| Responsible AI | NeurIPS 2026 | BKI, Friston-BKI, epistemic violence framing |
| AI Governance | ICML 2026 | Framework crosswalk, compliance theater |
| FAccT 2027 | Standalone | BKI white paper, Friston-BKI extended |

### Phase 2 support tasks

- [ ] Identify 1 external reviewer (not an agent — a human who will say "this is wrong")
- [ ] Research Georgia Tech / Emory AI governance faculty for potential affiliation
- [ ] Submit NCCoE-style comment to next NIST public comment period (repurpose existing draft)

---

## Phase 3: Citation Flywheel (Oct 2026–Mar 2027)

**Goal**: First external citation. 5+ papers on arXiv. Workshop presentation.

### Publication queue (submit as ready)

| Paper | Venue | Notes |
|-------|-------|-------|
| **Base120: Pre-Hoc Operator Commitment** | arXiv cs.AI | Needs completeness argument from corpus |
| **Coordination Bus: Append-Only Multi-Agent** | SoCC / arXiv cs.DC | Systems paper with real operational data |
| **Token Budget Governance** | arXiv cs.AI | Novel framing: cost as safety |
| **Agentic Identity Failures Taxonomy** | arXiv cs.MA | Reference paper, will attract citations |
| **Benchmark Decay and the Goodhart Trap** | arXiv cs.LG | Timely, connects to measurement theory corpus |
| **VERUM: Append-Only Governance Sovereignty** | arXiv cs.CR | Strengthen with Lamport/Merkle/Szabo from corpus |

### Flywheel mechanics

- `/daily-research` monitors Semantic Scholar for citations and related work
- Each citation triggers: read citing paper → write response or extension → submit
- Each new paper cites prior HUMMBL papers → self-reinforcing corpus
- Blog posts on hummbl.io drive practitioner traffic to arXiv papers

### Consolidation

| Action | Papers affected |
|--------|----------------|
| **Merge** Ashby Governance (211L) + Ashby Proof Sketch (166L) | → single Ashby paper |
| **Merge** BKI Governance (358L) into Friston-BKI | → Friston version is stronger |
| **Merge** Phantom Authority (338L) + Depth Laundering (530L) | → publish as companion pair |
| **Retire** Compliance Theater (204L) | → fold into BKI paper |
| **Repurpose** NCCoE Comment (299L) | → blog post or next NIST comment period |

---

## Phase 4: Institute-Equivalent (Q2–Q4 2027)

**Goal**: Recognized research presence. Option on institutional affiliation. Co-authored paper.

### Three paths (not mutually exclusive)

**Path A: Solo Lab (Gwern model)**
- Publish under "HUMMBL, LLC" with no institutional affiliation
- The body of work IS the credibility
- Lowest friction, highest autonomy
- Risk: slower citation accumulation without institutional signal

**Path B: Research Affiliate**
- Approach Georgia Tech, Emory, or Georgia State faculty with published papers
- "Visiting Researcher" or "Research Affiliate" — costs the university nothing
- Institutional address on papers, access to student co-authors
- Requires: 3+ published papers and a faculty champion

**Path C: Micro-Institute**
- HUMMBL Research Institute, LLC (or division of HUMMBL LLC)
- 1-3 people: Reuben + 1 co-author + agent fleet
- Can hire a part-time research assistant (PhD student, contractor)
- Requires: revenue from consulting or grants to fund the position

### Milestones for Phase 4

- [ ] 5+ papers on arXiv with Semantic Scholar profile
- [ ] 1+ external citation
- [ ] 1+ workshop or conference presentation
- [ ] 1+ co-authored paper (with human co-author)
- [ ] Decision: Path A, B, or C

---

## Paper Inventory (ranked by readiness)

### Tier A — Near-publishable (1-2 editing passes to arXiv)

| # | Title | Lines | LaTeX | Target |
|---|-------|-------|-------|--------|
| 1 | Governance Receipts: Human-Readable Audit Artifacts | 746 | No | CHI 2027 |
| 2 | Governance Tuple: Atomic Record for Auditable AI | 735 | Yes | AAMAS / arXiv |
| 3 | Coordination Bus: Append-Only Multi-Agent Systems | 576 | No | SoCC / arXiv |
| 4 | CRAI 2026: Typed Tuple Profile | 555 | Yes | CRAI 2026 |
| 5 | Depth Laundering: Exploiting Unbounded Delegation | 530 | No | USENIX / arXiv |
| 6 | Identity Recovery in Agentic AI Systems | 524 | No | AAMAS / arXiv |

### Tier B — Solid drafts (needs sections + related work)

| # | Title | Lines | Target |
|---|-------|-------|--------|
| 7 | Framework Crosswalk: NIST/EU/ISO/OWASP | 467 | IEEE AI Gov |
| 8 | Kill Switch: Formal Safety State Machine | 414 | SafeAI @ AAAI |
| 9 | BKI Governance: Belonging as Compliance Prerequisite | 358 | FAccT |
| 10 | Base120: Pre-Hoc Operator Commitment | 355 | arXiv |
| 11 | Phantom Authority: LLM Authorization Threat Model | 338 | USENIX |
| 12 | Agentic Identity Failures Taxonomy | 336 | AAMAS |
| 13 | Benchmark Decay and the Goodhart Trap | 326 | NeurIPS |
| 14 | Token Budget Governance | 315 | arXiv |
| 15 | Delegation Depth: Formal Authority Chain Bounds | 294 | AAMAS |

### Tier C — Early drafts (needs significant development)

| # | Title | Lines | Notes |
|---|-------|-------|-------|
| 16 | VERUM: Append-Only Governance Sovereignty | 269 | Strengthen with corpus XVIII |
| 17 | TRACE: Probe-Class Evaluation Harness | 250 | Needs evaluation results |
| 18 | Friston-BKI: Free Energy Suppression | ~180 | New, strong core |
| 19 | Ashby Requisite Variety Proof Sketch | ~166 | New, could publish as note |
| 20 | Compliance Theater | 204 | Fold into BKI paper |

### Tier D — Scaffolds

| # | Title | Notes |
|---|-------|-------|
| 21 | BKI White Paper | Corpus ready, no body |
| 22 | Sovereign Agents | Compose from Ashby + Ostrom + existing drafts |

### Non-academic

| Title | Type | Status |
|-------|------|--------|
| Ostrom Mapping Table | Sales artifact | Complete |
| NCCoE Public Comment | Policy submission | Deadline missed; repurpose |

---

## Infrastructure

### What exists

- **Corpus**: 59 entries, 19 clusters, all 6 Base120 families, verified citations (`hummbl-theory/foundations/`)
- **Package**: `hummbl-governance` on PyPI, 583 tests, Apache-2.0
- **Agent fleet**: Claude Code + Codex + Gemini, multi-agent coordination bus
- **Skills**: `/paper`, `/deep-research`, `/research-ingest`, `/preprint-scan`, `/bki-cite-audit`
- **2 LaTeX-ready papers**: CRAI 2026 Tuple Profile, Governance Tuple

### What's needed

- [ ] arXiv account + first submission
- [ ] ORCID registration
- [ ] Semantic Scholar profile (auto-generated after arXiv)
- [ ] hummbl.io/research page listing all papers with PDFs
- [ ] Citation monitoring in `/daily-research`
- [ ] 1 external human reviewer

---

## Metrics

| Metric | Current | Phase 1 | Phase 2 | Phase 3 | Phase 4 |
|--------|---------|---------|---------|---------|---------|
| Papers drafted | 24 | 24 | 24+ | 28+ | 30+ |
| Papers on arXiv | 0 | 3 | 5 | 8+ | 12+ |
| Peer-reviewed acceptances | 0 | 0 | 1+ | 2+ | 4+ |
| External citations | 0 | 0 | 0 | 1+ | 5+ |
| Semantic Scholar h-index | — | 0 | 0 | 1 | 2+ |
| Co-authored papers | 0 | 0 | 0 | 0 | 1+ |
| Workshop presentations | 0 | 0 | 1 | 2+ | 3+ |
| Corpus entries | 59 | 59 | 65+ | 75+ | 90+ |

---

## Principles

1. **Publish, don't polish.** A paper on arXiv with a flaw is worth more than a perfect draft in a private repo. Submit, then revise.
2. **The work is the institute.** No one cares about your affiliation if the research is rigorous and useful.
3. **Agents draft, humans judge.** The fleet produces at scale, but every claim needs at least one human who can say "this is wrong."
4. **Cite yourself.** Every new paper cites prior HUMMBL papers. The corpus is self-reinforcing.
5. **Blog the artifacts.** Not every output is a paper. Proof sketches, mapping tables, and frameworks are blog posts that drive practitioner traffic to the academic work.
6. **Recursive self-improvement is real.** Each session makes the next one faster. The corpus grows. The skills compound. The agents get better prompts. This is the moat.
