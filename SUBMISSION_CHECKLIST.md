# Submission Checklist — Pre-arXiv / Pre-Conference

Use this checklist before submitting any HUMMBL paper. Every item must be checked or explicitly waived with justification.

---

## 1. Content

- [ ] **Abstract** is under 250 words and states the result, not just the topic
- [ ] **Every claim** has a citation, an `[ESTIMATE: basis]` tag, or a `[STATUS: PROPOSED]` tag
- [ ] **Every citation** is verified real (author, year, title, venue all correct)
- [ ] **No unsourced statistics** — every number has a link, a derivation, or an estimate tag
- [ ] **Status tags** are accurate — nothing marked `[LIVE]` that isn't shipped; nothing marked `[VERIFIED]` without external validation
- [ ] **Claims cross-checked** against `CLAIMS.md` — any new claim added there
- [ ] **Gaps acknowledged** — relevant entries from `GAPS.md` mentioned as limitations or future work
- [ ] **Negative result N2 (Ubuntu universality)** — if citing Ubuntu, presented as one of several convergent traditions

## 2. Citations

- [ ] **arXiv IDs verified**: for every arXiv citation, confirm the paper title matches the ID
- [ ] **No phantom citations**: every `\cite{}` or `[Author Year]` reference exists in the bibliography
- [ ] **Self-citations**: prior HUMMBL papers cited where relevant (builds citation network)
- [ ] **Recency**: at least 2 citations from 2024 or later (shows engagement with current literature)
- [ ] **Preprint flag**: any preprint (arXiv, SSRN, bioRxiv) flagged as `[preprint]` — not presented as peer-reviewed

## 3. Formatting

- [ ] **Author line**: "Reuben Bowlby, HUMMBL LLC" (or co-authors if applicable)
- [ ] **ORCID**: included once registered
- [ ] **License**: CC-BY-4.0 for arXiv papers (allows redistribution with attribution)
- [ ] **LaTeX**: if venue requires it, `.tex` version compiled without errors
- [ ] **Page limit**: checked against venue requirements
- [ ] **Anonymization**: if double-blind venue, all self-identifying references removed

## 4. Technical

- [ ] **Mathematical notation** is consistent throughout (same symbol always means the same thing)
- [ ] **Definitions before use**: every symbol defined before first use
- [ ] **Proof steps**: no logical gaps in proof sketches — each step follows from the previous
- [ ] **Code references**: any reference to `hummbl-governance` includes version number and PyPI link
- [ ] **Reproducibility**: if empirical, data and code availability statement included

## 5. Pre-submission

- [ ] **External review**: at least 1 human (not an AI agent) has read the paper and provided feedback
- [ ] **Spell check**: run a spell checker (not just rely on LLM grammar)
- [ ] **PDF renders correctly**: margins, figures, tables all within bounds
- [ ] **arXiv category selected**: cs.AI, cs.CY, cs.CR, cs.MA, or cs.SE as appropriate
- [ ] **Cross-list categories**: add secondary categories if the paper spans domains

## 6. Post-submission

- [ ] **arXiv ID recorded** in `ROADMAP.md` paper inventory
- [ ] **Semantic Scholar** profile checked for auto-indexing (usually 24-48h after arXiv)
- [ ] **Blog companion** drafted for hummbl.io (practitioner-accessible version)
- [ ] **CLAIMS.md updated** with any new claims and their arXiv evidence link
- [ ] **Citation monitoring** added to `/daily-research` watchlist

---

## Venue-Specific Notes

### arXiv (no peer review)
- Fastest path to publication. No deadline, no review, immediate visibility.
- Use for: position papers, proof sketches, threat models, formal frameworks.
- License: CC-BY-4.0 recommended (non-exclusive — you retain rights).

### CHI (HCI)
- Deadline ~September for following year conference.
- Wants: user studies, design implications, practical systems with human evaluation.
- Best fit: Governance Receipts, HCI Governance Receipts.

### FAccT (Fairness, Accountability, Transparency)
- Deadline ~January for June conference.
- Wants: sociotechnical analysis, formal fairness frameworks, critical perspectives.
- Best fit: Friston-BKI, BKI Governance, Compliance Theater.

### AAAI SafeAI Workshop
- Deadline ~October for February workshop.
- Wants: formal safety, verification, alignment.
- Best fit: Kill Switch, Delegation Depth, Phantom Authority.

### AAMAS (Multi-Agent Systems)
- Deadline ~October for May conference.
- Wants: formal multi-agent coordination, protocols, trust.
- Best fit: Governance Tuple, Coordination Bus, Agentic Identity.

### USENIX Security
- Deadline ~February and ~September (two cycles).
- Wants: novel attacks, defenses, empirical evaluation.
- Best fit: Depth Laundering, Phantom Authority.
