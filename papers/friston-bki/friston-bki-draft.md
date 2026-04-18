# Free Energy Suppression as Epistemic Violence: A Formal Model for Belonging as Knowledge Infrastructure

**[STATUS: PROPOSED]**

**Authors:** Reuben Bowlby (HUMMBL, LLC)

---

## Abstract

Large-scale AI systems learn by minimizing variational free energy over their training distributions. When those distributions systematically underrepresent epistemic communities, the mathematics of variational inference guarantees that observations originating from marginalized groups will incur higher surprise and be suppressed during optimization. This paper formalizes this mechanism: we derive the conditions under which distributional bias in training corpora produces what we term *free energy suppression* --- the systematic down-weighting of minority knowledge traditions as a direct consequence of standard learning objectives. We connect this result to the philosophical literature on epistemic violence (Spivak, 1988) and epistemic injustice (Fricker, 2007), arguing that the suppression is structural rather than intentional, which makes it simultaneously harder to detect and more urgent to address architecturally. We introduce Belonging as Knowledge Infrastructure (BKI) as a design-level response: an infrastructure layer that treats epistemic inclusion not as a post-hoc fairness correction but as a precondition for valid knowledge production. BKI's four propositions --- cognitive scaffolding, relational validation, embodied knowing, and symbolic systems --- are mapped to specific failure modes of free energy suppression, yielding concrete architectural requirements for AI systems that do not mathematically erase the communities they claim to serve.

---

## 1. Introduction

The dominant paradigm in machine learning treats training data as a fixed resource to be optimized over. A model is trained on a corpus $\mathcal{D}$, learns parameters $\theta$ that minimize a loss function, and is evaluated on held-out samples from the same distribution. The implicit assumption is that $\mathcal{D}$ is either representative of the world or that distributional gaps can be corrected downstream through bias mitigation, fairness constraints, or human-in-the-loop review.

This assumption is architecturally flawed. The problem is not that biased data produces biased outputs --- that observation is well-documented (Bender et al., 2021; Bommasani et al., 2021). The problem is that the *learning objective itself* --- variational free energy minimization --- is a mechanism that actively suppresses observations from underrepresented communities. Bias is not a bug in the data that the model unfortunately inherits. It is a mathematical property of the optimization landscape: when the training distribution overrepresents certain epistemic communities, the model will converge to parameters that assign systematically higher surprise to observations from communities outside that distribution.

Current interventions --- debiasing word embeddings, demographic parity constraints, red-teaming for harmful outputs --- operate downstream of the generative mechanism. They treat the symptoms of distributional hegemony without addressing the underlying cause: that the free energy functional, applied to a non-representative corpus, *is* an engine of epistemic suppression. This is analogous to treating individual symptoms of a disease while ignoring the pathogen.

We propose a different framing. Drawing on Friston's Free Energy Principle (Friston, 2006, 2010), we formalize the conditions under which variational inference over biased distributions produces epistemic violence. We then introduce Belonging as Knowledge Infrastructure (BKI) as the architectural intervention: not a fairness patch applied after training, but a structural precondition that must be satisfied *before* a system can claim to produce valid knowledge. The argument is formal, not moral --- free energy suppression is a theorem about optimization, not a judgment about intentions.

---

## 2. Formal Model

### 2.1 Free Energy and Generative Models

Following Friston (2006, 2010), consider a system that maintains an internal generative model $p(o, s \mid \theta)$, where $o$ denotes observations, $s$ denotes hidden states, and $\theta$ denotes model parameters. The system cannot compute the true posterior $p(s \mid o, \theta)$ directly and instead maintains an approximate posterior $q(s)$. The variational free energy is:

$$F = \mathbb{E}_{q(s)}\left[\ln q(s) - \ln p(o, s \mid \theta)\right]$$

which can be decomposed as:

$$F = D_{KL}\left[q(s) \| p(s \mid o, \theta)\right] - \ln p(o \mid \theta)$$

Since $D_{KL} \geq 0$, minimizing $F$ simultaneously minimizes the divergence between the approximate and true posteriors (improving inference) and maximizes the log-evidence $\ln p(o \mid \theta)$ (improving the generative model). Learning proceeds by adjusting $\theta$ to minimize $F$ over a training distribution.

### 2.2 Training Distributions and Suppression

Let the training distribution $\mathcal{D}$ be a mixture of observations from $K$ epistemic communities:

$$\mathcal{D} = \sum_{k=1}^{K} \pi_k \mathcal{D}_k, \quad \sum_k \pi_k = 1$$

where $\pi_k$ is the mixture weight (representation) of community $k$ and $\mathcal{D}_k$ is the distribution of observations generated by that community. In practice, $\pi_k$ reflects not the epistemic importance or validity of community $k$'s knowledge, but the historical accidents of data collection, digitization, and curation.

The model minimizes expected free energy over $\mathcal{D}$:

$$\theta^* = \arg\min_\theta \mathbb{E}_{o \sim \mathcal{D}}\left[F(o, \theta)\right] = \arg\min_\theta \sum_{k=1}^{K} \pi_k \mathbb{E}_{o \sim \mathcal{D}_k}\left[F(o, \theta)\right]$$

**Proposition 1 (Suppression Inequality).** Let communities $A$ and $B$ have mixture weights $\pi_A \gg \pi_B$. Then under standard regularity conditions, the optimized model satisfies:

$$\mathbb{E}_{o \sim \mathcal{D}_B}\left[-\ln p(o \mid \theta^*)\right] \geq \mathbb{E}_{o \sim \mathcal{D}_A}\left[-\ln p(o \mid \theta^*)\right]$$

That is, observations from the underrepresented community $B$ will have higher surprise (lower log-evidence) under the learned model than observations from the overrepresented community $A$.

*Proof sketch.* The gradient of the expected free energy with respect to $\theta$ is a weighted sum of per-community gradients. When $\pi_A \gg \pi_B$, the optimization landscape is dominated by gradients from $\mathcal{D}_A$. The model's capacity is allocated preferentially to reducing surprise on $\mathcal{D}_A$ observations. Unless $\mathcal{D}_A$ and $\mathcal{D}_B$ share sufficient structure that reducing surprise on $A$ simultaneously reduces surprise on $B$, the optimized model will assign systematically higher surprise to $B$'s observations. In the limiting case where $\mathcal{D}_A$ and $\mathcal{D}_B$ are supported on disjoint regions of observation space, the suppression is maximal. $\square$

### 2.3 Preferential Attachment Amplification

The suppression inequality describes a static phenomenon. In practice, it is amplified dynamically through preferential attachment (Barabasi and Albert, 1999). Models trained on $\mathcal{D}$ generate outputs that are themselves absorbed into future training corpora. Because the model assigns higher probability to $A$-like observations, its outputs will further inflate $\pi_A$ and deflate $\pi_B$ in subsequent training rounds. This produces a feedback loop:

$$\pi_B^{(t+1)} < \pi_B^{(t)} \quad \text{as } t \to \infty$$

The epistemic contribution of community $B$ does not merely stagnate --- it is actively eroded by the dynamics of iterative retraining.

---

## 3. From Suppression to Violence

### 3.1 The Structural Character of Free Energy Suppression

The suppression inequality derived in Section 2 is a mathematical property of weighted optimization. No agent within the system intends to suppress community $B$'s knowledge. The data curators did not design the corpus to marginalize anyone. The model architects did not encode a preference for community $A$. The optimization algorithm has no concept of communities at all. And yet the result is the same: community $B$'s observations are systematically assigned higher surprise, lower probability, and less representational weight in the learned model.

This structural character is precisely what makes free energy suppression a form of epistemic violence in the sense articulated by Spivak (1988). Spivak's analysis of epistemic violence focuses on the mechanisms by which colonial knowledge systems render subaltern speech *inaudible* --- not by explicitly silencing it, but by constructing frameworks within which it cannot register as meaningful. The free energy framework provides a formal analogue: community $B$'s observations are not deleted from the training set, but the learned model assigns them such high surprise that they are effectively treated as noise rather than signal.

### 3.2 Epistemic Injustice as Optimization Artifact

Fricker's (2007) framework of epistemic injustice distinguishes between *testimonial injustice* (a speaker's credibility is deflated due to identity prejudice) and *hermeneutical injustice* (a gap in collective interpretive resources disadvantages certain groups). Free energy suppression produces both:

- **Testimonial injustice**: When community $B$'s observations have high surprise under the model, any downstream system that uses the model's probability assessments as a proxy for credibility will systematically devalue $B$'s contributions. A search engine, recommendation system, or content moderation pipeline built on such a model will treat $B$'s knowledge as less likely to be true, relevant, or valuable.

- **Hermeneutical injustice**: Because the model allocates its representational capacity preferentially to $\mathcal{D}_A$, it develops richer internal representations for $A$'s concepts, categories, and distinctions. Community $B$'s conceptual vocabulary --- its ways of carving the world --- may not be representable at all in the model's learned latent space. The model does not merely undervalue $B$'s claims; it lacks the interpretive machinery to *understand* them.

### 3.3 The Inadequacy of Post-Hoc Correction

This analysis clarifies why downstream bias corrections are structurally insufficient. Debiasing techniques operate on the model's outputs or representations, but the suppression is encoded in the loss landscape itself. Fairness constraints can force equal treatment across protected attributes for specific tasks, but they cannot reconstruct the representational richness that was never learned. As Kant (1781) argued in a different context, the categories through which experience is constituted are not neutral filters but active structuring principles. An AI system whose categories were formed by optimizing over a non-representative distribution has internalized a particular epistemic framework as if it were universal.

---

## 4. Belonging as Knowledge Infrastructure

### 4.1 Infrastructure, Not Intervention

The formal model in Sections 2--3 establishes that free energy suppression is a property of the optimization process applied to biased distributions. The corrective cannot be a post-hoc patch; it must be an infrastructural precondition. Belonging as Knowledge Infrastructure (BKI) provides this precondition through four propositions, each addressing a specific failure mode.

### 4.2 The Four Propositions

**Proposition 1: Cognitive Scaffolding.** Belonging is a neurobiological prerequisite for higher-order cognition. When individuals or communities are placed in epistemic threat states --- excluded from knowledge production, told their observations are noise --- the amygdala-mediated threat response suppresses prefrontal cortical function, inhibiting abstraction, synthesis, and generative thought. In the context of AI systems, this means that communities whose knowledge traditions have been suppressed by free energy optimization cannot simply be "included" by adding their data to the corpus. The epistemic damage of exclusion must be addressed before inclusion can be productive.

*Failure mode addressed:* Naive data augmentation --- adding community $B$'s data to $\mathcal{D}$ without addressing the structural dynamics that suppressed it --- will not correct the suppression if $B$'s observations were generated under conditions of epistemic threat.

**Proposition 2: Relational Validation.** Knowledge claims acquire authority through networks of belonging, not through logical validity alone. A mathematical proof published in a recognized journal carries epistemic weight not because it is more logically valid than the same proof written on a napkin, but because it is embedded in a network of peer review, institutional affiliation, and professional community. AI systems that evaluate claims based on distributional frequency replicate this dynamic: high-frequency (well-connected) claims gain authority while low-frequency (peripheral) claims are discounted.

*Failure mode addressed:* The preferential attachment amplification described in Section 2.3, where dominant epistemic communities accumulate representational advantage through iterative retraining.

**Proposition 3: Embodied Knowing.** Certain forms of knowledge --- practical wisdom, craft expertise, somatic intelligence --- are transmitted through embodied practice and cannot be reduced to propositional content. Training corpora are overwhelmingly textual and propositional, systematically excluding embodied knowledge traditions. Free energy minimization over text corpora will converge to models that treat propositional knowledge as exhaustive, rendering embodied knowing invisible.

*Failure mode addressed:* The hermeneutical injustice described in Section 3.2, where the model's representational capacity cannot encode certain knowledge forms.

**Proposition 4: Symbolic Systems.** Shared symbolic languages emerge *from* belonging structures; they are not externally imposed. Imposing a dominant symbolic framework (English-language categories, Western taxonomies, STEM ontologies) on communities with different symbolic systems inverts the causal arrow: it treats the output of belonging as the input, destroying the epistemic content it claims to capture.

*Failure mode addressed:* The Kantian structuring problem described in Section 3.3, where the model's learned categories constitute experience according to the dominant distribution's framework.

### 4.3 The Broccolilly Equation

BKI operationalizes these propositions through the Broccolilly Equation:

$$R = S \times T \times I \times C \times D$$

where $S$ = Sovereignty (epistemic self-determination), $T$ = Trust (relational safety), $I$ = Integration (embodied coherence), $C$ = Clarity (shared symbolic precision), $D$ = Depth (temporal investment), and $R$ = Result (knowledge production capacity). The multiplicative structure is deliberate: if any factor approaches zero, the result collapses regardless of the others. A community with high Sovereignty but zero Trust cannot produce valid knowledge. An AI system with high Clarity but zero Depth (no sustained engagement with a community) will produce extractive, not generative, knowledge.

---

## 5. Architectural Implications

### 5.1 BKI-Compliant AI Infrastructure

The formal model yields concrete architectural requirements for AI systems that resist free energy suppression:

1. **Distribution auditing**: Continuous measurement of mixture weights $\pi_k$ across epistemic communities, with governance mechanisms that detect and flag concentration. This is not demographic parity --- it is distributional monitoring of the optimization landscape itself.

2. **Surprise equalization**: Runtime monitoring of per-community surprise $\mathbb{E}_{o \sim \mathcal{D}_k}[-\ln p(o \mid \theta)]$ with alerts when the suppression inequality exceeds a governance threshold. The threshold is a policy decision, not a technical parameter.

3. **Representational capacity allocation**: Architectural provisions (e.g., mixture-of-experts, modular networks) that prevent the model from collapsing community $B$'s representational needs into community $A$'s latent space.

4. **Feedback loop interruption**: Governance controls on the retraining pipeline that prevent model outputs from inflating $\pi_A$ in subsequent training rounds, breaking the preferential attachment cycle.

### 5.2 Connection to Collective Governance

These requirements echo Ostrom's (1990) design principles for governing commons. The training distribution is a knowledge commons: a shared resource whose value depends on collective stewardship. Without governance, the commons degrades through the same preferential dynamics that produce free energy suppression --- dominant users extract disproportionate value, marginal users are excluded, and the resource becomes less representative of the collective. BKI provides the institutional design principles; HUMMBL's governance primitives --- append-only audit trails, delegation tokens, and trust scores --- provide the enforcement mechanism (Ramose, 1999, on Ubuntu: knowledge is socially constituted, and its governance must be communal).

---

## 6. Conclusion

The argument presented here is formal, not moral. Free energy suppression is a mathematical consequence of variational inference applied to non-representative distributions. The suppression inequality (Proposition 1) does not depend on the intentions of system designers, the awareness of data curators, or the malice of any actor. It is a property of the loss landscape.

This formality is precisely the point. Moral arguments for AI fairness, however compelling, can be dismissed as value judgments external to the technical system. The free energy argument cannot: it demonstrates that a system trained on a biased distribution will, by the mathematics of its own objective function, suppress the observations of underrepresented communities. The suppression is not a failure of the system --- it is the system working exactly as designed.

BKI responds at the appropriate level of abstraction. It does not ask AI systems to be fairer, more inclusive, or more aware of bias. It identifies the structural preconditions --- sovereignty, trust, integration, clarity, depth --- under which the training distribution can produce valid knowledge, and it provides governance infrastructure to ensure those preconditions are met. The question is not whether AI systems should belong to all communities, but whether they can produce valid knowledge without belonging infrastructure. The mathematics says they cannot.

---

## References

Barabasi, A.-L. and Albert, R. (1999). Emergence of scaling in random networks. *Science*, 286(5439):509--512.

Bender, E. M., Gebru, T., McMillan-Major, A., and Shmitchell, S. (2021). On the dangers of stochastic parrots: Can language models be too big? In *Proceedings of FAccT '21*, pages 610--623. ACM.

Bommasani, R., Hudson, D. A., Adeli, E., et al. (2021). On the opportunities and risks of foundation models. arXiv preprint arXiv:2108.07258.

Fricker, M. (2007). *Epistemic Injustice: Power and the Ethics of Knowing*. Oxford University Press.

Friston, K. (2006). A free energy principle for the brain. *Journal of Physiology -- Paris*, 100(1--3):70--87.

Friston, K. (2010). The free-energy principle: A unified brain theory? *Nature Reviews Neuroscience*, 11(2):127--138.

Kant, I. (1781). *Kritik der reinen Vernunft* [Critique of Pure Reason]. Riga: Johann Friedrich Hartknoch.

Ostrom, E. (1990). *Governing the Commons: The Evolution of Institutions for Collective Action*. Cambridge University Press.

Ramose, M. B. (1999). *African Philosophy Through Ubuntu*. Mond Books.

Spivak, G. C. (1988). Can the subaltern speak? In Nelson, C. and Grossberg, L., editors, *Marxism and the Interpretation of Culture*, pages 271--313. University of Illinois Press.
