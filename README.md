# Hello, I'm José Arturo Ornelas Brand 👋

### Architect | Truth-seeker

> *Distinguishing between the world we mold by desire and the universe that exists by its own right.*

Architect by training, independent researcher by vocation. I build computable, verifiable formalisations of concepts that usually live in philosophy — duality, synthesis, opposition, pre-logical states — and connect them to deterministic neurosymbolic architectures via prime factorisation and a quaternionic operator $\mathcal{O} = \{0, 1, +, i, j, k\}$ that unifies Boolean, fuzzy, modal, trivalent, ordinal, and probabilistic logics as dimensional restrictions of a single structure.

The research program has a single organising question: **what stays invariant when the perspective changes, and what is shaped by the perspective itself?** The G-lattice of P11 answers this formally — the real component of a quaternionic truth value is invariant under the $\mathrm{SU}(2)$ context action (objective truth), while the imaginary components carry the epistemic character that depends on the observer (mold by desire).

The research program is organised in two layers:

- **Computational substrate (P1–P4)** — prime factorisation as a neurosymbolic bridge, its generative/discovery functions, tools for tracking representation evolution, and empirical evidence for layered semantic duality.
- **Formal algebraic framework (P11–P13)** — a G-lattice on $[0,1] \times [-1,1]^3$ with an $\mathrm{SU}(2)$ group action; its non-commutative extension; the synthesis operation that generates truth from opposites; and the pre-logical states where the truth axis is undefined.

---

## Foundation: computational substrate

### P1 — Triadic Neurosymbolic Engine

> **Prime factorisation as a neurosymbolic bridge.**

Projects continuous embeddings into a discrete algebraic space for deterministic verification. Establishes the projection $\Phi: \mathbb{R}^d \to \mathbb{N}$ that maps concepts to squarefree integers, where divisibility encodes subsumption, $\mathrm{lcm}$ encodes composition, and $\gcd$ encodes abductive gap analysis — three operations not expressible under cosine similarity.

[![Repo](https://img.shields.io/badge/GitHub-Repo-blue?logo=github)](https://github.com/arturoornelasb/Triadic-Neurosymbolic-Engine)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19205805.svg)](https://doi.org/10.5281/zenodo.19205805)
[![PyPI](https://img.shields.io/badge/PyPI-triadic--engine-blue?logo=pypi)](https://pypi.org/project/triadic-engine/)

**The problem it tackles.** Cosine similarity reduces a relationship between two concepts to one number — *"King and Queen are 0.87 similar"* — but cannot answer the *logical* questions that downstream systems actually need: does King contain every feature of Queen? Which features do they share? Which differentiate them? The framework projects each concept into a single integer whose prime factors are its semantic features, so those three questions become exact integer operations: divisibility, $\gcd$, and $\mathrm{lcm}$ — deterministic, explainable, and natively expressible in SQL or Prolog.

**Open questions.**
- **Choosing $k$ in a principled way.** The useful regime $k \in [6, 12]$ for the LSH projection is empirical. Is there a corpus-intrinsic criterion (e.g. based on the spectral structure of the embedding covariance) that selects optimal $k$ a priori, or is the choice irreducibly heuristic?
- **When does LSH containment coincide with semantic subsumption?** The method guarantees an exact equivalence between divisibility and LSH bucket containment, but bucket containment is only a *probabilistic* proxy for genuine semantic subsumption — changing the random seed can reverse the relationship. Under which conditions on the embedding geometry do the two coincide reliably?
- **A theoretical bound on the false-positive rate.** Random hyperplanes give a baseline FPR of $(3/4)^k$ for spurious subsumption. PCA-directed projections achieve $\approx 0.62\times$ that baseline empirically, but no closed-form bound exists. Can the FPR for a given projection mode be expressed analytically in terms of the spectral structure of the corpus?
- **Cross-modal generalisation.** The framework was evaluated on text embeddings (\texttt{sentence-transformers}). Does the projection $\Phi$ transfer to vision-language (CLIP), audio, or knowledge-graph embeddings without re-engineering?

---

### P2 — TriadicGPT

> **End-to-end prime factorisation in a generative language model.**

A 40M-parameter GPT augmented with a triadic projection head trained jointly with language modelling. The head learns discrete prime-factor signatures alongside next-token prediction, producing algebraically verifiable representations as a side effect of training — at a measured cost of $+1.7\%$ perplexity. Includes a standalone PyPI package (`triadic-head`) usable as a drop-in for any HuggingFace transformer.

[![Repo](https://img.shields.io/badge/GitHub-Repo-blue?logo=github)](https://github.com/arturoornelasb/triadic-microgpt)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19206545.svg)](https://doi.org/10.5281/zenodo.19206545)
[![PyPI](https://img.shields.io/badge/PyPI-triadic--head-blue?logo=pypi)](https://pypi.org/project/triadic-head/)

**The problem it tackles.** P1 projects *frozen* sentence-transformer embeddings into prime space *post-hoc* — the language model has no incentive to produce representations amenable to prime factorisation, and the projection step can only preserve whatever structure happens to exist in the frozen embeddings. P2 closes the loop: by training the triadic head end-to-end with a four-component objective (diversity, contrastive, entropy regularisation, embedding alignment), the LM is forced to organise its hidden states for clean discretisation. The empirical outcome is that subsumption, analogy, and composition become *learned* algebraic capabilities rather than projection artefacts: 98% analogy verification (50/51 quads), 100% signature uniqueness, $+0.038 \pm 0.005$ semantic gap (multi-seed, $n=3$), and — with a differentiable subsumption loss combined with the iFSQ activation $2\sigma(1.6x)-1$ — up to $87.1\%$ held-out subsumption and $100\%$ at $k=64$, while preserving language quality. A transfer experiment attaching the head to pre-trained GPT-2 with InfoNCE alignment closes 48% of the gap to P1's post-hoc PCA, identifying the alignment-loss formulation (not embedding quality) as the primary bottleneck.

**Open questions.**
- **The semantic-grounding gap.** External evaluation on SimLex-999 reveals that the system does not capture graded semantic similarity: neither Jaccard on binary signatures ($\rho = -0.012$) nor cosine on the continuous projections ($\rho = 0.046$, $p = 0.14$) achieves significance. The kill criterion K1 fails honestly, positioning TriadicGPT as an **algebraic encoding** rather than an algebraic semantics. What additional training signal — graded contrastive, multi-task similarity regression, or curriculum from pre-trained sentence transformers — would bridge this without sacrificing the discrete algebraic guarantees?
- **The sparsity–compositionality trade-off.** Dense signatures ($\sim 30$ active bits / 64) preserve compositional structure (analogy gap $+15.4$~pp between valid and invalid quads); sparse signatures ($\sim 16$ active bits) enable subsumption detection (false-positive ratio $3.7$–$26.5\times$ above the $(3/4)^k$ random baseline) but degrade compositionality. No configuration satisfies both. Is this trade-off inherent — overlapping codes are needed to distinguish related compositions, sparse codes for informative bit-subset relations — or could a hybrid architecture (dense bits for analogy + sparse bits for subsumption + a routing mechanism) decouple them?
- **Scale–algebra interaction.** A 355M-parameter run with the full triadic loss pipeline (D-A19) restores $76.9\%$ subsumption (895 test pairs) and $100\%$ analogy verification, refuting the apparent regression at scale (D-A17, $1.7\%$ subsumption with alignment-only loss). Yet the gap remains to the 40M model's $98.3\%$ subsumption. What sparsity-preserving training regime would maintain the empirically optimal $\sim 42\%$ ternary zero rate at backbone scales beyond 355M, where the ternary distribution skews toward near-binary?
- **Loss–embedding interaction.** MSE alignment dominates from-scratch (TinyStories, 512D) — gap $+0.020$ — while InfoNCE catastrophically loses semantic ordering in the same setting, but dominates on pre-trained GPT-2 (768D) at $+0.076$. The interaction is structural: contrastive losses require global cluster structure to mine meaningful positives; MSE only requires local pairwise relationships. Is there a quantitative property of the embedding space (spectral concentration, local-density variance, Wasserstein distance to a reference clustering) that *predicts* which alignment loss will succeed before training?

---

### P3 — reptimeline

> **Tracking discrete representation evolution during neural network training.**

A backend-agnostic Python library that captures per-code lifecycle events (births, deaths, connections, phase transitions), discovers structure bottom-up (anti-correlated duals, dependency chains, three-way AND-gate interactions), and verifies that discovered features have selective causal effects via bootstrap confidence intervals, permutation tests, and Benjamini–Hochberg FDR correction. Validated on three architecturally distinct backends: a 32-bit binary autoencoder on MNIST, sparse-autoencoder features on Pythia-70M, and the 63-bit neurosymbolic projection head from P2.

[![Repo](https://img.shields.io/badge/GitHub-Repo-blue?logo=github)](https://github.com/arturoornelasb/reptimeline)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19208672.svg)](https://doi.org/10.5281/zenodo.19208672)
[![PyPI](https://img.shields.io/badge/PyPI-reptimeline-blue?logo=pypi)](https://pypi.org/project/reptimeline/)

**The problem it tackles.** Standard training-monitoring tools (WandB, TensorBoard, codebook-utilisation metrics) report scalar aggregates: they tell the practitioner *that* something changed at step 27,500, but not *what* changed. When codebook collapse happens, the loss curve shows a kink — but which codes died, did they die together, was a phase transition involved, which concepts lost their unique representations? These questions require per-code temporal analysis that no existing tool provides for arbitrary discrete representations. reptimeline operates on the discrete codes themselves, requires no predefined labels, discovers structure bottom-up, and verifies causality — all through a single API that works on any system producing a mapping from concepts to discrete code vectors.

**Open questions.**
- **Triadic discovery scaling.** Three-way AND-gate detection is $O(K^3)$ in the number of active bits. For sparse autoencoders with thousands of active features it becomes prohibitive without sampling or parallelisation. Is there a principled candidate-pruning criterion — e.g. a marginal-information bound or a tensor-decomposition surrogate — that preserves the genuine triadic interactions while discarding most triples *a priori*?
- **Distinguishing sparsity from selectivity.** On Pythia-70M, 8 of 16 tested SAE features showed zero cross-activation — perfect by definition, but indistinguishable from the artefact of an SAE sparse code that simply never fires for non-labelled concepts. What additional intervention or null model would separate genuine causal selectivity from a sparsity ceiling?
- **From causal selectivity to predictive utility.** The 8 finite-selectivity SAE features are causally meaningful (zeroing them changes predictions selectively) but using them for next-token prediction yielded $-0.13\%$ (embedding-based) and $-4.20\%$ (MLP-based) versus baseline. Why does selective causal influence at the feature level fail to translate to gains at the prediction level — is the obstacle distributional, compositional, or an artefact of the read-out architecture?
- **Beyond binary codes.** The discovery operations (duals, dependencies, triadic AND-gates) are currently formulated on $\{0, 1\}$ codes; FSQ levels and ternary $\{-1, 0, +1\}$ representations require pre-binarisation, which discards information. Can the lifecycle and discovery framework be extended natively to ternary or general categorical codes without collapsing back to binary?

---

### P4 — Layered Ontology of Semantic Duality

> **14+ candidate dualities across 6 algebraic layers.**

A formal ontological framework in which conceptual complexity emerges from 14+ candidate dualities organised across 6 algebraic layers (Boolean, Fuzzy, Ordinal, Modal, Trivalent, Probabilistic), grounded in 72 semantic primitives connected by a DAG of 133+ dependency edges. Evaluated through three independent methodologies: domain analysis across 8 disciplines + 3 negative controls (Astrology, Alchemy, Phrenology) using a composite 6-metric Domain Validity Score; Bayesian model comparison yielding BF~=~121.4 (decisive) over the reversed ordering; and a neurosymbolic GPT-2 Medium model augmented with a 72-bit triadic head that learns the primitive structure at 90.8\% bit accuracy while preserving general language ability (PPL = 31.95, identical to baseline).

[![Repo](https://img.shields.io/badge/GitHub-Repo-blue?logo=github)](https://github.com/arturoornelasb/triadic-emergent-duality)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19375167.svg)](https://doi.org/10.5281/zenodo.19375167)
[![HF V5](https://img.shields.io/badge/%F0%9F%A4%97-triadic--gpt2--medium--v5-yellow)](https://huggingface.co/arturoornelasb/triadic-gpt2-medium-v5)
[![HF V6](https://img.shields.io/badge/%F0%9F%A4%97-triadic--gpt2--medium--v6-yellow)](https://huggingface.co/arturoornelasb/triadic-gpt2-medium-v6)
[![HF V8](https://img.shields.io/badge/%F0%9F%A4%97-triadic--gpt2--medium--v8-yellow)](https://huggingface.co/arturoornelasb/triadic-gpt2-medium-v8)
[![HF V9](https://img.shields.io/badge/%F0%9F%A4%97-triadic--gptneo--125m--v9-yellow)](https://huggingface.co/arturoornelasb/triadic-gptneo-125m-v9)

**The problem it tackles.** Existing semantic-primitive frameworks either lack formal algebraic structure (Wierzbicka's NSM offers $\sim 65$ primes but no algebraic chain), validate compositional semantics without addressing emergence (DisCoCat, FrameNet), or produce large knowledge graphs without an ordering principle (ConceptNet's 34 relation types). The framework proposes that conceptual complexity is not flat but *layered*, with each layer requiring algebraic structure that the previous one cannot express — degree from existence, comparison from degree, possibility from order, valuation from possibility, observation from valuation. The empirical contribution is to test this layered claim across three independent regimes (domain classifications, Bayesian ordering against alternatives like Hegel and Peirce, and neural representation learning), reporting both confirmatory and null results: 8/8 positive domains discriminate from 3/3 negative controls (gap $0.233$, robust across all weight configurations); the proposed ordering is decisive against the reversed sequence (BF $= 121.4$) but only weakly preferred over Hegel ($1.14$) and Peirce ($1.95$); the algebraic Markov-blanket structure is preserved by construction in the learned 72-bit codes (Q13 algebraic, $0/500{,}000$ pair violations) and the quaternionic product axioms (closure, associativity, ${ij=k}$, non-commutativity) are verified over the learned coordinates (Q18, T1--T7 PASS) — but the model does *not* recover any fixed layer ordering (Q1 null, $p = 0.71$), and a model-derived second rater does *not* recover expert D-A-N classifications ($\kappa \in [-0.082, 0.111]$ across 8 domains, Q32). What the model *does* learn is relational structure: regla de tres analogies preserved with cosine $0.997$, and a sharp phase transition during training ($p = 0.0004$) that high-resolution X-ray reveals as a *cascade* of bit activations rather than an instantaneous reorganisation.

**Open questions.**
- **External inter-rater validation (K2 protocol).** All D-A-N classifications were made by a single rater. Independent human-vs-human data exists for only 1/9 domains (Mathematics). A complementary model-vs-human probe (Q32) computed Cohen's $\kappa$ across 8 of 9 domains, with all values in the slight-to-poor range ($\kappa \le 0.11$, Philosophy highest, Chemistry lowest). The model does *not* substitute for human inter-rater validation. What level of human-vs-human $\kappa$ would be required to consider the layered ontology externally validated, and would systematic disagreements reveal genuine ambiguity in the D-A-N codebook or single-author bias in the original classifications?
- **Layer ordering vs cascade.** Q1 was reformulated after high-resolution telescopic X-ray analysis on two architectures (GPT-2 Medium v8 and GPT-Neo 125M v9): emergence is not a fixed L1$\to$L6 sequence but a *cascade* of bit activations whose specific order varies by architecture (v9: middle layers L3--L5 first, ontological extremes L1/L6 last; v8: L1 first, L2 last). What *is* conserved cross-architecture is the cascade pattern itself (gradual wave propagation of $\sim$45 steps in v9 vs $\sim$145 in v8, never instantaneous). Is there any training regime, scale, or corpus under which a *universal* layer ordering would be recovered, or is the cascade-without-ordering the genuine empirical pattern and the L1$\to$L6 sequence a frame-relative philosophical convention?
- **A 15th internal operator (D15).** The per-layer count of internal operators is asymmetric: $(1, 1, 2, 2, 1, 0)$ — layer 6 (probabilistic) has none. The framework documentation formally proposes **D15: Collapse/Superposition** as the missing internal operator, with \texttt{temporal\_obs} and \texttt{eterno\_obs} reassigned as anchors, closing the pattern to the symmetric $(1, 1, 2, 2, 1, 1)$. D15 is not yet empirically validated. What probe would *distinguish* D15 (operating on the observer's collapsed/superposed state) from D14 (Sujeto/Objeto, the transition that *generates* the observer), and what would constitute evidence for or against the symmetric pattern beyond aesthetic appeal?
- **Algebraic structure preserved, statistical structure absent.** The unique-prime assignment guarantees by construction that coprime concept interiors satisfy $\gcd(\mu_1, \mu_2) = 1$ — Q13 algebraic verifies the implementation correctly preserves this (PASS 100\% on 500K pairs). But Q13 MI shows the *statistical* counterpart fails: partial-correlation recovery of DAG edges is at chance (Mann--Whitney $p = 0.82$ in v8, $p = 0.018$ borderline in v9), and only the layer-hierarchy ratio test (T2) consistently passes. Why does the algebraic d-separation property not lift to statistical d-separation in the learned codes — is this an inherent limitation of frozen-base training, or does an end-to-end training regime (P2's TriadicGPT direction) recover the statistical structure as well?
- **Cross-linguistic universality.** All 72 primitives are named and evaluated in a Spanish-language conceptual frame. The framework pre-registers a falsification criterion: if independently derived primitives from a typologically distant language (Mandarin, Swahili) produce $<40\%$ overlap with the current inventory, the claims must be restricted to "Western philosophical tradition" rather than "universal ontology". The criterion has not yet been tested. Which methodology (independent expert derivation, distributional bottom-up extraction from monolingual corpora, or a translation-then-cluster approach) would constitute a fair empirical test of universality vs. linguistic bias?
- **Scale--algebra interaction.** The 355M-parameter GPT-2 Medium achieves 76.9\% subsumption with the full triadic loss pipeline; the 40M-parameter TriadicGPT in P2 reaches 98.3\% on a comparable test set. The same direction of degradation appears in v6 (extended corpus): bit accuracy drops from 90.8\% (v5, 72 primitives) to 80.9\% (v6, 2{,}166 concepts) but unique-signature collapse is dramatic ($100\% \to 21.4\%$), with the model functioning as a *family classifier* rather than an individual discriminator. What sparsity-preserving training regime (entropy schedule, head capacity, anchor density) would let the algebraic guarantees scale to backbones beyond 355M and concept counts beyond a few thousand?

---

## Formal framework: quaternionic logic

### P11 — Quaternionic Logic

> **A G-lattice unifying Boolean and fuzzy frameworks.**

Constructs a residuated lattice on $[0,1] \times [-1,1]^3$ equipped with an $\mathrm{SU}(2)$ group action by quaternionic conjugation. Six known logics (Boolean, Gödel fuzzy, Gödel–Kripke modal, Kleene trivalent, ordinal, probabilistic) are recovered as dimensional projections. Soundness and completeness are proved via reduction to Gödel logic with involutive negation.

[![Repo](https://img.shields.io/badge/GitHub-Repo-blue?logo=github)](https://github.com/arturoornelasb/quaternionic-logic-paper)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19562014.svg)](https://doi.org/10.5281/zenodo.19562014)

---

### P11.1 — Non-Commutative Quaternionic t-Norm

> **A trilemma on Hamilton multiplication.**

Investigates whether the Hamilton product can serve as a genuinely non-commutative conjunction. Establishes positive results (bilateral identity, associativity, emergent non-commutativity) and proves a **theorem**: for any monoidal operation on a subset of $V = [0,1] \times [-1,1]^3$, at most two of {associativity, non-commutativity, compatible lattice order} can hold simultaneously.

[![Repo](https://img.shields.io/badge/GitHub-Repo-blue?logo=github)](https://github.com/arturoornelasb/nc-quaternionic-tnorm-paper)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19561407.svg)](https://doi.org/10.5281/zenodo.19561407)

---

### P12 — Duality Synthesis

> **How opposites generate new truth.**

Develops the synthesis operation on the prime algebra: when two opposites $C_1, C_2$ are combined, the result $\mathrm{lcm}(\Phi(C_1), \Phi(C_2))$ is a genuinely higher-layer concept, not a reducible combination. Shows that opposites generate new truth at higher algebraic layers through an irreducibly second-order gap operation.

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19561634.svg)](https://doi.org/10.5281/zenodo.19561634)

---

### P13 — Pre-Logical States

> **How reasoning operates before truth exists.**

Formalises pre-logical states — points in $V$ where the truth axis is undefined — and proves that information emerges as the compound concept of the pre-logical/logical duality. Substrate independence demonstrated across four domains (emergency response, scientific discovery, moral reasoning, creative process).

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19561722.svg)](https://doi.org/10.5281/zenodo.19561722)

---

## 📫 Open invitation to collaborate

This research program is deliberately interdisciplinary. It touches algebraic logic, quaternion and Clifford algebra, neurosymbolic AI, cognitive science, random matrix theory, and philosophy of information — no single specialist community covers the whole of it. Advancing it further requires dialogue with researchers who bring rigour and depth from each of those fields.

I extend an open invitation to the scientific and academic community — at any level, in any of the relevant disciplines — to collaborate: verify a proof, challenge a hypothesis, test a prediction empirically, extend the framework into a new domain, or simply think out loud about where it connects to your own work. Critical engagement is welcome and valued.

**Seeking arXiv endorsement.** As an independent researcher without institutional affiliation, I am currently seeking endorsement to cross-post this work on arXiv in the relevant subject areas (primarily `math.LO`, `math.RA`, `cs.LO`, `cs.AI`, and `cond-mat.stat-mech`). If you are an arXiv endorser in any of these categories and consider the work appropriate after reviewing a paper, an endorsement would be much appreciated.

- 📧 **Email:** [arturoornelas62@gmail.com](mailto:arturoornelas62@gmail.com)
- ✖️ **X (Twitter):** [@Ornelord](https://x.com/Ornelord)
