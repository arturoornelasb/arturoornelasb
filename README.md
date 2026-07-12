# José Arturo Ornelas Brand

### Independent researcher — random-matrix physics of learning

> One control parameter drags a system's spectrum between the universal fixed points of random matrix theory. I measure that statement with the same instruments on two substrates: **freely vibrating plates** and **training neural networks** — and I publish the hypothesis before the test, the gates with the numbers, and the negatives with the positives.

---

## The random-matrix program (2026)

Six preprints, published as one arc: a falsifiable physics hypothesis, its full open-source test campaign, the quantitative transfer to neural networks, the formal unification — and the payoff: the program's diagnostic turned into a metrological figure of merit.

**→ [Read the illustrated program report](https://arturoornelasb.github.io/rmt-program-report.html)** — how the six papers relate, a reading guide, the predictions scoreboard (what held, what broke), and the D₂ bridge, with figures from the papers.

**1 · Why Rosenzweig–Porter? Evanescent coupling and a random matrix hypothesis for intermediate statistics in freely vibrating plates**
&nbsp;&nbsp;[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.21313838.svg)](https://doi.org/10.5281/zenodo.21313838)
The mechanism (H = H₀ + λV from free-edge evanescent coupling), eight testable predictions, and a preregistered eigenvector fractal dimension D₂ = 0.76 ± 0.15.

**2 · Open-source finite-element tests of the Rosenzweig–Porter hypothesis: preliminary results**
&nbsp;&nbsp;[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.21314728.svg)](https://doi.org/10.5281/zenodo.21314728)
Twenty preregistered experiment campaigns executing the registered program: the boundary-controlled transition confirmed; a three-tier boundary-adaptedness hierarchy; the D₂ signature exposed as a truncation-protocol artifact, with a real, ordered multifractal residue in its place; a mechanical GOE→GUE crossover with its antiunitary protection theorem, completing at ≈1,500 RPM for a decimeter silicone disk; and a designed plate assembly whose fabricated D₂ lands inside the neural-network band.

**3 · A random-matrix account of structure formation in neural networks**
&nbsp;&nbsp;[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.21314469.svg)](https://doi.org/10.5281/zenodo.21314469)
The same account, quantitative on the AI side: level repulsion is absent in dense nets but fabricable under forced sector cooperation (causal dose–response, capacity-attenuation law); two routes to the unitary class (the causal mask, exactly; a directional task, genuinely); and the fabricated transition is genuine Rosenzweig–Porter multifractality — D₂ = 0.76, co-transitioning with the spacing statistic on the same Hessian.

**4 · Effective-rank collapse marks the semantic phase transition in neural networks**
&nbsp;&nbsp;[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.21314143.svg)](https://doi.org/10.5281/zenodo.21314143)
The transferring spectral signature as an order parameter — from frozen transformer heads to a trained 7B (weights, live activations, training) — with a grokking decoupling and a label-corruption dose–response: the coupling, not the magnitude, is the semantic signature.

**5 · The dynamic selector and the formal operad are one object**
&nbsp;&nbsp;[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.21314570.svg)](https://doi.org/10.5281/zenodo.21314570)
The bridge made literal: instantiating the random-matrix model with an integer Clifford algebra's grades, kernels, and gate, the signatures survive and the composition laws are machine-checked (Coq/Rocq, re-verified at runtime).

**6 · Multifractality as a sensing resource: a D2 figure of merit for Rosenzweig-Porter systems, and a lattice platform**
&nbsp;&nbsp;[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.21316839.svg)](https://doi.org/10.5281/zenodo.21316839)
The payoff: composing F_Q = 4·chi_f with Kravtsov's exact RP result makes D₂ an operational sensing figure of merit — QFI enhancement exponent 1 − D₂ for multifractal random states under local couplings, confirmed at 4/4 preregistered gates, its boundaries measured (geometric fractality alone: no effect; critical PBRM: extends), with an operator design rule and a constructed cold-atom platform.

## Code — everything is reproducible

**[plates-rp-fem](https://github.com/arturoornelasb/plates-rp-fem)** — the full FEM campaign behind paper 2: certified Argyris / C⁰ interior-penalty eigensolvers, the preregistered experiment registry (E1–E20, frozen readings committed *before* each run — the git history is the preregistration trail), and the manuscript. Python, CPU-only.

**[rp-qfi-sensing](https://github.com/arturoornelasb/rp-qfi-sensing)** — companion of paper 6: the gRP/PBRM/Sierpinski fidelity-susceptibility experiments with frozen readings and certified eigensolvers.

**[rmt-signatures](https://github.com/arturoornelasb/rmt-signatures)** — code + derived-data companion of papers 3–5: per-phase experiment scripts, findings records, and figures — including the machine-checked operad proof (`operad_osynth_mech.v`: 56 Qed, 0 Admitted, one typing parameter; `coqchk`-verified).

## Method

- **Preregistration as a workflow, not a form** — every experiment ships with a frozen reading in its header before it runs; amendments are declared, dated, and diffed in git.
- **Measurement-based accuracy gates** — two-mesh, cross-instrument, and penalty-robustness certification decide what counts, not asymptotic hope.
- **Negatives are first-class results** — the strongest finding of the campaign is a claim that *failed* under the true operator, and exactly how.
- **Formal claims are machine-checked** — if a paper says "proved," there is a `.v` file and a kernel re-checker exit code you can reproduce.

---

## Earlier work (2025–2026)

Neurosymbolic substrate and a quaternionic logic framework — the program that led here.

**Triadic Neurosymbolic Engine** · [repo](https://github.com/arturoornelasb/Triadic-Neurosymbolic-Engine) · [doi:10.5281/zenodo.19205805](https://doi.org/10.5281/zenodo.19205805)
Prime factorisation as a neurosymbolic bridge: subsumption, composition, and abduction as exact integer operations.

**TriadicGPT** · [repo](https://github.com/arturoornelasb/triadic-microgpt) · [doi:10.5281/zenodo.19206545](https://doi.org/10.5281/zenodo.19206545)
The projection learned end-to-end in a generative LM (`triadic-head` on PyPI).

**reptimeline** · [repo](https://github.com/arturoornelasb/reptimeline) · [doi:10.5281/zenodo.19208672](https://doi.org/10.5281/zenodo.19208672)
Tooling for tracking representation evolution across training.

**Layered Ontology of Semantic Duality** · [repo](https://github.com/arturoornelasb/triadic-emergent-duality) · [doi:10.5281/zenodo.19375167](https://doi.org/10.5281/zenodo.19375167)
Empirical evidence for layered semantic duality in transformers.

**Quaternionic Logic series** · [repo](https://github.com/arturoornelasb/quaternionic-logic-paper) · [doi:10.5281/zenodo.19562014](https://doi.org/10.5281/zenodo.19562014) · [t-norm](https://doi.org/10.5281/zenodo.19561407) · [synthesis](https://doi.org/10.5281/zenodo.19561634) · [pre-logical](https://doi.org/10.5281/zenodo.19561722)
A G-lattice on [0,1]×[−1,1]³ with an SU(2) context action unifying Boolean, fuzzy, modal, trivalent, ordinal, and probabilistic logics.

---

## Collaboration

The program spans random matrix theory, wave chaos, elastodynamics, deep-learning theory, Clifford algebra, and formal verification — no single community covers all of it. If you want to verify a proof, challenge a gate, test a prediction (the 1,500-RPM silicone rotor is waiting for a lab), or connect this to your own work: critical engagement is welcome.

**Seeking arXiv endorsement** — as an independent researcher I am looking for endorsement to cross-post in `cond-mat.stat-mech`, `nlin.CD`, `cs.LG`, and `math.LO`. If you endorse in these areas and the work holds up to your reading, it would be much appreciated.

📧 [arturoornelas62@gmail.com](mailto:arturoornelas62@gmail.com) · ✖️ [@Ornelord](https://x.com/Ornelord)
