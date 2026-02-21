# Results

## What the Study Measured

441 interaction threads. 1,980 steering operations. One practitioner across task types spanning technical writing, strategic analysis, code generation, research synthesis, and structured argumentation. Every thread was scored on a 20-point rubric with four weighted dimensions: Relevance (30%), Completeness (20%), Actionability (10%), Signal Density (40%). Each threaded session was paired against a single-shot baseline prompt on the same task — same input context, same model, no structural scaffolding — to isolate the effect of the framework itself.

Signal Density carries the most weight because it measures the ratio of usable, non-redundant content per response token. A high-relevance, low-density response is verbose alignment. High density with low relevance is confident noise. The rubric penalizes both. The sessions that scored highest combined tight constraint with focused direction — outputs that answered exactly what was asked and nothing they weren't.

---

## Performance Deltas vs. Single-Shot Baseline

| Metric | Baseline (mean) | Framework (mean) | Delta | n |
|---|---|---|---|---|
| Composite Score (20-pt rubric) | 11.4 | 15.3 | **+34%** | 441 threads |
| Signal Density | 9.1 | 12.9 | **+42%** | 441 threads |
| Objective Fulfillment | 10.7 | 14.0 | **+31%** | 441 threads |
| Relevance | 10.9 | 14.1 | **+29%** | 441 threads |
| Completeness | 11.2 | 14.3 | **+28%** | 441 threads |
| Actionability | 10.5 | 13.9 | **+32%** | 441 threads |

**Notes:** All deltas are averages across n=441. Sessions under 3 moves were excluded from the density analysis (n=38 excluded; aggregate results held within 2%). Baseline prompts were not intentionally poor — they were the best single-shot version of each task the practitioner could write. The gap measures scaffolding yield against competent prompting, not against careless prompting.

---

## The Three Highest-Impact Moves

### Meta (+38% average composite contribution vs. sessions without it)

Meta is metacognitive regulation: the practitioner audits the session mid-thread and redirects before errors compound. It is the lowest-frequency move in the corpus at 3.5% of operations and the highest-leverage one. The mechanism is specific. When a session accumulates drift — the model producing topically adjacent but directionally wrong output — Meta resets the frame without discarding prior context. A well-placed Meta move functions like a mid-flight course correction: the destination stays constant, but the trajectory gets recalculated.

Sessions that included at least one Meta operation scored an average of +38% higher composite than sessions that ran straight through without it. Sessions that included Meta after a detected drift event — identifiable in retrospect by a drop in signal density at moves 3–5 — recovered their trajectory in 83% of cases within two subsequent moves.

### Decompose (+29% average composite contribution)

Decompose breaks a complex request into sub-components before generation begins. The performance gain is not mysterious. Complex tasks with multiple implicit dependencies — a strategic memo, a multi-part technical spec, an argument with three independent claims — cause a model to make implicit sequencing choices. Decompose makes those choices explicit and controllable.

In threads where Decompose appeared early (moves 1–3), signal density was 22% higher than in threads where it appeared mid-session or not at all. Front-loading structural decomposition lets every downstream move operate on a smaller, well-defined surface. Refine on a decomposed component is more precise than Refine on an amorphous whole.

### Refine (+24% average composite contribution)

Refine is iterative tightening: the practitioner identifies what the model produced correctly and constrains the next generation to build from that valid portion. Unlike Decompose (structural) or Meta (directional), Refine is local — it operates on the most recent output rather than the session architecture.

Refine's performance advantage concentrates in threads with 5+ moves. Below five moves, Refine contributes modestly. Above five, sessions using Refine at least twice per five-move interval maintain signal density 18% higher than sessions that don't. Long contexts allow early constraints to lose attention weight. Refine periodically re-anchors the model to what has already been validated.

---

## Domain Variation

Not all task types responded equally to the framework. The strongest absolute gains appeared in:

**Strategic analysis and structured argumentation (+41% composite).** These tasks require multi-step reasoning with explicit dependencies between claims. Single-shot prompting either produces superficial coverage or arbitrarily prioritizes one line of argument. Decompose + Recurse sequences force exhaustive treatment. Meta identifies when the model is hedging rather than committing.

**Technical documentation (+36% composite).** Documentation tasks are deceptively hard — they feel simple until they need to be correct at every level simultaneously. The framework's scope-control moves (Scope Tighten, Add Constraints) directly address the model's default tendency to write comprehensive-sounding documentation that omits specific edge cases.

**Research synthesis (+33% composite).** Synthesis tasks require the model to hold multiple source threads simultaneously and produce a coherent integrative output. Without scaffolding, the model defaults to serial summarization. Decompose + Compare + Recurse sequences produced genuine synthesis — claims differentiated across sources, tensions named, integrative conclusions offered — at a rate single-shot prompting did not approach.

**Creative writing showed the smallest gains (+14% composite).** This was expected. Creative tasks have no ground truth for objective fulfillment. The rubric's Actionability dimension barely applies. The framework's gains here came almost entirely from signal density — less padding, more narrative content per token — rather than from objective completion rates.

---

## What the Numbers Establish and What They Cannot

The data establishes that structured, iterative steering produces substantially better outputs than competent single-shot prompting across most task domains, measured by a specific rubric, for one practitioner, during one study period.

The data does not establish generalizability across practitioners. This is a single-subject study. The practitioner designed the framework, wrote the rubric, and executed all sessions. Selection effects and scoring artifacts cannot be fully controlled. The +34% composite delta is real within these conditions. How much of it transfers to practitioners without the framework designer's background is unknown and requires multi-practitioner replication to answer.

The data does not establish causation at the move level. Correlation between move presence and performance is strong. The mechanisms proposed here — what each move does to the session's attention distribution — are mechanistically plausible and analytically consistent with the patterns, but they are not experimentally isolated. A controlled ablation study with multiple practitioners would be required to make causal claims at that level of specificity.

What the study does establish: the loop matters more than the weight. The same model, given the same input context, produces substantially different outputs depending on whether the interaction is a single shot or a structured sequence. That finding is robust within the study's conditions and consistent with what controlled studies on Chain-of-Thought prompting have shown in narrower domains. The framework is a causal candidate. It is not yet a proven cause.

---

*Recursive Prompting™ by Seth Robins — Recursive Intelligence™ | [CC BY-SA 4.0](LICENSE.md)*
