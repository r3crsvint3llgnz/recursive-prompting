# Recursive Prompting

**Author:** Seth Robins — Recursive Intelligence™  
**Version:** 2.0 | **License:** [CC BY-SA 4.0](LICENSE.md)

---

Large language models are stochastic systems. Every token is a probability estimate conditioned on what came before. Over long contexts and complex reasoning tasks, that process drifts — not randomly, but in predictable, diagnosable patterns. Standard prompting has no mechanism for catching or correcting that drift. Recursive Prompting does.

This framework defines a vocabulary of 13 steering moves, a structural loop for applying them, and a diagnostic protocol for recognizing when to intervene. It is grounded in post-hoc analysis of 441 interaction threads comprising 1,980 discrete steering operations. The performance data is single-practitioner (n=1) and explicitly carries that limitation. The mechanical framework does not depend on that data to be useful.

---

## Read the Series

The framework is documented in five sequential sections. Each section assumes the previous one.

| Section | File                                                                            | Contents                                                                                                                      |
| ------- | ------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| 01      | [Introduction: Why Simple Prompting Fails](01-introduction-problem-focused.md)  | The technical failure modes of autoregressive generation; why CoT, ToT, and LtM are insufficient; the case for a control loop |
| 02      | [The Core Loop: Probe, Scope, Refine](02-core-loop-probe-scope-refine.md)       | All 13 steering moves with mechanical definitions; the default three-move sequence; performance data; use-case patterns       |
| 03      | [The Recursive Self-Improving Prompt](03-recursive-self-improving-prompt.md)    | Delegating architectural work to the model itself; two templates with full annotation; the SELF-REFINE framework              |
| 04      | [Implementation, Diagnostics, and Checklists](04-implementation-diagnostics.md) | Eight failure patterns with corrective moves; warning signs; three session checklists; quick-reference table                  |
| 05      | [The Architect's Choice](05-architects-choice.md)                               | Synthesis and conclusion                                                                                                      |

---

## Reference Documents

- **[Steering Moves Reference](move_types_reference.md)** — All 13 moves with definitions, failure modes they solve, and example prompts
- **[Pattern Templates v1](pattern_templates_v1.md)** — Validated multi-move sequences for recurring task types
- **[Learning Path](learning_path.md)** — Structured entry points by experience level
- **[Methodology](methodology.md)** — How the 441-thread dataset was constructed and analyzed
- **[Abstract](abstract.md)** — Research summary
- **[References](references.md)** — Citations and further reading
- **[Complete Whitepaper](complete_whitepaper.md)** — Unified single-document version of the full framework

---

## Empirical Summary

The data comes from 441 interaction threads analyzed post-hoc to extract recurring structural patterns. Observed deltas against unstructured single-shot baselines: +34% outcome quality (subjective, 20-point rubric), +42% signal density, +31% objective fulfillment rate. The three highest-impact moves by frequency and effect size: **Meta**, **Decompose**, **Refine**.

Single-practitioner limitations apply throughout. These numbers establish a foundation for future multi-user controlled trials, not a universal claim.

---

_Recursive Prompting™ is a trademark of Seth Robins / Recursive Intelligence™. See [TRADEMARK.md](TRADEMARK.md) for usage terms._
