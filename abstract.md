# Abstract

This paper formalizes Recursive Prompting as a systematic framework for maintaining intent across complex language model interactions. It is grounded in post-hoc analysis of 441 discrete interaction threads comprising 1,980 individual steering operations, conducted by a single practitioner. That scope carries the standard limitations of n=1 research: the findings are reproducible within the practitioner's context and carry no claim of universal generalizability without multi-user controlled replication.

The analysis extracted 20 recurring structural patterns from the thread corpus and distilled them into 13 steering moves — atomic operations that each address a specific class of model failure. Performance measurement used a 20-point mechanical rubric assessing relevance, completeness, actionability, and signal density against unstructured single-shot baselines. Observed deltas: +34% outcome quality (subjective composite), +42% signal density, +31% objective fulfillment rate. The three highest-impact moves by effect size were metacognitive regulation (Meta), structural decomposition (Decompose), and iterative refinement (Refine).

The central argument is not that structured prompting improves outputs. That is already established in the literature (Wei et al., 2022; Yao et al., 2023). The argument here is more specific: that a named vocabulary of steering moves, applied within a feedback loop, produces diagnosable and correctable failure patterns rather than opaque failures that require starting over. The framework's value is not that it prevents drift — it is that it makes drift visible and reversible.

Section 03 of this series draws on the SELF-REFINE framework (Madaan et al., 2023) for performance data on recursive self-improvement architectures. Those figures are external to the n=1 dataset and are cited accordingly. The broader methodology and taxonomy are derived entirely from the practitioner's own thread analysis.

A unified reference list appears in [references.md](references.md).

---

*Recursive Prompting™ by Seth Robins — Recursive Intelligence™ | [CC BY-SA 4.0](LICENSE.md)*
