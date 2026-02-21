# Recursive Prompting: A Mechanical Framework for Reliable Model Steering

**Author:** Seth Robins — Recursive Intelligence™  
**Date:** February 2026  
**Version:** 2.0  
**License:** [CC BY-SA 4.0](LICENSE.md) | **Trademark:** Recursive Prompting™ (Recursive Intelligence™)

---

## Abstract

This paper formalizes Recursive Prompting as a systematic framework for maintaining intent across complex language model interactions. It is grounded in post-hoc analysis of 441 discrete interaction threads comprising 1,980 individual steering operations, conducted by a single practitioner (n=1). The analysis identified 13 steering moves — atomic operations each addressing a specific class of model failure — and 20 recurring multi-move patterns distilled into validated templates across five functional domains.

Performance was measured using a 20-point rubric (relevance 30%, completeness 20%, actionability 10%, signal density 40%) against unstructured single-shot baselines. Observed deltas: +34% composite outcome quality, +42% signal density, +31% objective fulfillment rate. The three highest-impact moves by effect size: metacognitive regulation (Meta), structural decomposition (Decompose), and iterative refinement (Refine).

The central argument extends beyond "structured prompting improves outputs," which the literature already supports (Wei et al., 2022; Yao et al., 2023). The argument here is more specific: that a named vocabulary of steering moves, applied within a feedback loop, makes model failure diagnosable and reversible rather than opaque. The framework's value is not that it prevents drift. It is that it makes drift visible.

Section 4 of this paper draws on the SELF-REFINE framework (Madaan et al., 2023) for performance data on recursive self-improvement architectures. Those figures are external to the n=1 dataset and cited accordingly. The taxonomy and methodology derive entirely from the practitioner's own thread analysis.

Standard n=1 limitations apply throughout.

---

## 1. Why Simple Prompting Fails

Large language models are stochastic systems masquerading as deterministic ones. Every token is a probability estimate conditioned on what came before. Over long contexts and complex reasoning tasks, that process accumulates error. Documented error rates in production contexts: 27% for citations, 15% for numerical data. By the time a model completes a complex reasoning task, it has drifted from the original intent — not because of poor prompting, but because of how the architecture distributes attention over extending context.

Three existing frameworks attempt to address this. Chain-of-Thought prompting (Wei et al., 2022) externalizes intermediate reasoning steps and improves performance on multi-step tasks. But CoT remains linear: an error in step two cascades through steps three and four. On complex planning tasks, CoT fails on the first step 60% of the time. Tree-of-Thoughts (Yao et al., 2023) adds branching and backtracking, outperforming CoT by approximately 25% on the same tasks — but remains single-pass at each node, preserving the core vulnerability to local context drift. Least-to-Most prompting (Zhou et al., 2022) decomposes hierarchically and improves coherence over long chains, but better ordering does not eliminate autoregressive noise within each subproblem.

All three frameworks are fundamentally one-directional: input to reasoning to output. The assumption is that a well-structured prompt will produce a well-structured output. That assumption fails when context is long, reasoning is complex, or stakes require accuracy.

What changes the dynamic is a control loop. Instead of prompt to output, the interaction becomes: generate, inspect, constrain, regenerate. Each cycle re-anchors the model to verified state. The model does not stop drifting because it became more capable. It stops drifting because it is forcibly re-grounded at regular intervals. Recursive Prompting formalizes that loop.

---

## 2. The Framework: 13 Steering Moves

Each move addresses a specific, recurring failure mode. They are listed in functional order, not frequency order.

**Probe.** Generate multiple options or alternatives before committing to any. Solves premature commitment — the model's default of locking onto the first plausible interpretation of a request. Without a probe step, all subsequent work optimizes from an unexamined anchor.

*Example:* "Give me 5 different structural approaches to this argument, each with a different underlying assumption."

**Scope Tighten.** Narrow focus to a specific subset, constraint, or slice of the problem. Without a scope constraint, the model attends to the entire problem space simultaneously and produces output superficially relevant to everything and not specifically useful for anything. Scope Tighten forces the attention window onto one target.

*Example:* "Focus only on the onboarding flow. Ignore everything downstream of first login."

**Scope Loosen.** Widen perspective to include broader context, adjacent concerns, or system-level effects. Solves tunnel vision — optimization of a part that destroys the whole. Applied after Scope Tighten to check for systemic side effects of a locally correct decision.

*Example:* "Zoom out: how does this change affect the end-to-end flow, not just the screen we were working on?"

**Format Control.** Specify the output structure before generating content. Solves unusable data — the right content in the wrong structure makes the content inaccessible. Front-loading the format reduces structural hallucinations because the model fills a defined container rather than inventing one.

*Example:* "Structure as a table: column 1 is the decision, column 2 is the trade-off, column 3 is the reversibility."

**Seed.** Establish initial context, constraints, and success criteria explicitly. Without a seed, the model assumes a context. The model's assumed context and the practitioner's actual context diverge silently from the first token.

*Example:* "Context: B2B SaaS, mid-market, 18-month average deal cycle. Goal: one-page competitive positioning brief. Success: a salesperson can hand this to a prospect asking 'why not Competitor X.'"

**Refine.** Improve existing content with a specific directive. Generic refinement requests produce stylistic variation, not substantive improvement. Refine must target a specific quality bar or failure mode to produce targeted improvement.

*Example:* "Refine this paragraph: remove every generic statement, back each claim with a specific mechanism or example, cut word count by 25%."

**Add Constraints.** Introduce specific limitations or requirements before or during generation. Without constraints, the model converges toward its training distribution average — competent and unremarkable. Constraints force the model away from the statistical average toward the specific context.

*Example:* "Add constraints: maximum 150 words, three bullets, no hedging language, no advice that would apply to any company."

**Role Shift.** Adopt a specific perspective, persona, or stakeholder viewpoint. The model's default perspective is its own. Role Shift forces it to simulate a different mind — revealing risks and gaps the default perspective cannot see.

*Example:* "Evaluate this proposal as the CFO who has seen three failed implementations of this type. What specifically would concern you?"

**Recurse.** Build iteratively on previous outputs, targeting specific under-developed sections. Single-shot prompts cannot go deep because they distribute attention across all components. Recurse allows targeted depth on selected components without disturbing the rest.

*Example:* "Expand only the third section. Add: why this matters mechanically, a concrete example, and what failure looks like when this step is skipped."

**Meta.** Step back to examine the goal, process, or framing itself rather than advancing the current thread. Meta is the only move that can catch goal displacement — all other moves assume the current goal is correct. It detects when stated goal and actual work have diverged without explicit redirection.

*Example:* "Pause. What is the actual decision being made here, and is this analysis addressing it? Name the gap between what we've been working on and what I originally asked for."

**Compare.** Evaluate multiple options against explicit criteria. Solves the quiet reassertion of the original anchor — the tendency for the first Probe option to win by default. Compare forces a rubric onto subjective options and makes the basis for selection explicit.

*Example:* "Compare these three approaches on implementation time, reversibility, and risk to existing users. Score 1-5 on each and explain any score below 3."

**Decompose.** Break a complex problem into a deterministic sequence of sub-problems where each output becomes the input for the next. A model asked to produce a complex output in one shot attends to all components at once and gives each one inadequate depth. Decompose ensures each sub-problem receives full attention.

*Example:* "Break this project into discrete phases. For each: the specific deliverable, the inputs required, and the constraint that must be satisfied before moving to the next phase."

**Hypothesis.** Form and label testable predictions or assumptions explicitly. Solves assumption creep — unvalidated guesses treated as established facts that compound through subsequent reasoning. Hypothesis forces uncertain claims to be labeled as uncertain before they generate downstream errors.

*Example:* "Identify the three most critical assumptions in this plan. For each: state it as a hypothesis, specify what evidence would confirm or falsify it, and rate current confidence."

---

## 3. The Core Loop

The minimal viable sequence for reliable output is three moves: **Probe → Scope Tighten → Refine**.

Probe generates the option space. Scope Tighten commits to one option and narrows to it completely. Refine improves the committed output against a specific quality bar. This sequence prevents the two most common failure modes simultaneously: premature commitment (solved by Probe) and undirected refinement (solved by the specific quality bar in Refine).

This is the default. It works for most tasks. The remaining 10 moves address specific failure modes this default does not cover.

### Selected Patterns by Difficulty

**Novice — Probe → Scope Tighten → Refine.** The default control loop. Use for 80% of standard tasks: drafting, summarizing, structuring, explaining.

**Practitioner — Seed → Probe → Role Shift.** The blind spot checker. Get the plan first, then force the model to attack its own work from an adversarial perspective. Use for high-stakes decisions and strategy work.

**Practitioner — Probe → Compare → Refine.** The decision assistant. Generate options, apply a rubric, polish the winner. Prevents subjective selection from appearing as objective evaluation.

**Expert — Meta → Decompose → Seed.** The project rescue. Use when a task feels stuck or undefined. Meta audits whether the goal is correct before Decompose breaks it into tractable parts.

**Expert — Scope Tighten → Scope Loosen → Recurse.** The zoom lens. Fix the specific problem precisely, then verify the fix doesn't break the system. Use for technical changes with systemic side effects.

---

## 4. The Recursive Self-Improving Prompt

The 13 moves require human judgment at each step. That overhead works when tasks are bounded and failures are visible. It becomes impractical for complex or ambiguous tasks where the failure mode is not predictable in advance.

The Recursive Self-Improving Prompt delegates the architectural work to the model itself. Instead of the human selecting which move applies, the model analyzes its own goal, identifies where it will fail, constructs a precise instruction set for itself, and executes against it.

When a model writes its own constraints and then executes against them, those constraints appear in context as model-generated content rather than external instructions. Abandoning self-generated constraints mid-execution has a higher probabilistic cost than abandoning externally-imposed instructions. The model's own context anchors it.

This principle underlies the SELF-REFINE framework (Madaan et al., 2023): the model generates its own feedback through a Generator → Critic → Refiner loop, requiring no additional training data. The improvement comes from the loop structure, not from changed weights. Observed performance improvements: mathematical reasoning 22.1% → 59.0%; complex constraint satisfaction (20-30 constraints) 4.4% → 61.3%.

### Template 1: The Master Recursive Formula

Use when you want the model to fully architect and execute a complex task in one response.

---

**GOAL:** `[YOUR OBJECTIVE]`

**(META):** Do not execute the goal yet. Act as a Senior Prompt Architect. Design a high-fidelity, recursive instruction set for yourself to achieve the goal above.

**PROTOCOL:**

1. **(PROBE):** Identify three semantic ambiguities or logic gaps in the goal that could lead to drift.
2. **(DECOMPOSE):** Break the task into a deterministic sequence of sub-problems where each output feeds the next.
3. **(ADD CONSTRAINTS):** Specify what counts as acceptable output — format, scope, signal quality, exclusions.
4. **(ROLE SHIFT):** Apply a Skeptical Critic layer to verify the internal logic of this prompt before execution.

**(RECURSE):** Execute the optimized prompt and deliver only the final, high-signal result.

---

### Template 2: The Convergent Recursive Loop

Use for extended multi-turn work where you want iterative progression with built-in navigation.

---

**GOAL:** `[YOUR OBJECTIVE]`

At each step:

**(A) PROGRESS:** Provide the best possible advance toward the goal given what has been established.

**(B) NEXT PROMPT:** Write the single follow-up prompt the user should send next to advance most efficiently. Write it as a prompt, not a description.

**(C) CONVERGE:** Evaluate how close the work is to the finished goal. If not converged, proceed. If converged, state it explicitly and stop.

---

The operationally important instruction is (B): the model is predicting which steering move it needs next and writing the prompt for you. This eliminates the human bottleneck at each cycle.

---

## 5. Implementation, Diagnostics, and Checklists

### Failure Patterns and Corrective Moves

| Symptom | Primary Fix | Supporting Fix |
|---|---|---|
| Output could apply to anyone | Add Constraints | Seed |
| Model went outside the task | Scope Tighten | Format Control |
| Stuck on first idea | Probe | Compare |
| Output is shallow or thin | Recurse (targeted) | Refine + Add Constraints |
| Confident but wrong specifics | Hypothesis | Scope Tighten |
| Instructions fading across session | Seed (full reset) | Meta |
| Completing form, not function | Role Shift | Decompose |
| Refinement spinning in place | Hypothesis (name the failure) | Compare |
| Affirmative preamble or hedges | Add Constraints | Format Control |
| Goal is unclear | Meta | Decompose |
| Task too complex for manual steering | Master Recursive Formula | — |

### Warning Signs — Act Before Full Failure

**Affirmative preamble.** Response opens with "Great question!" or restates the prompt. Apply Add Constraints: "Begin with the answer. No preamble."

**Caveat cascade.** Multiple consecutive paragraphs hedging. Apply Scope Tighten: "State claims directly. Qualify only where the uncertainty is operationally significant."

**The non-answer answer.** Background and framing without directly answering the question. Apply Scope Tighten + Meta: "Answer only the specific question. One paragraph. Then stop."

**Symmetrical conclusion.** Terminal statement of "both sides have merit." Apply Role Shift + Hypothesis: "Take the most defensible position. State it directly."

**Length inflation.** Output is longer but not more useful. Apply Refine: "Reduce by 40%. Preserve every claim with specific content. Eliminate everything else."

### Session Checklists

**Before starting:**
- [ ] Goal is a specific deliverable, not a subject area  
- [ ] Success criteria defined: what does "done" look like?  
- [ ] Output format, length, and exclusions specified  
- [ ] For complex tasks: consider using the Master Recursive Formula  

**Mid-session (every 3-5 exchanges):**
- [ ] Output still addresses the original goal  
- [ ] Original constraints still active in the model's behavior  
- [ ] Signal density still high; no inflation trend  
- [ ] Model not introducing assumptions you did not provide  

**Recovery:**
- [ ] Stop refining the current output — continuing a failed thread compounds the failure  
- [ ] Re-state the goal from scratch as if the model has no context  
- [ ] Apply Decompose: start with the first sub-step only  
- [ ] If goal is unclear: Meta first, before any other move  

---

## 6. Methodology

The analysis draws from 441 interaction threads accumulated over active practice — post-hoc analysis of real tasks on production models. The 441 threads produced 1,980 discrete steering operations classified into the 13-move taxonomy. A subset of 370 threads had sufficient depth (four or more sequential moves with measurable output progression) to support transition mapping.

**Extraction process.** Thread segmentation divided conversations into goal-oriented units. Structural stripping removed topical content to expose the underlying move sequence, enabling cross-domain comparison. A thread about software architecture and one about competitive strategy can exhibit the same structure: Probe → Scope Tighten → Decompose → Refine. The topics are noise; the sequences are the signal. Classification assigned each prompt one primary move; where a prompt executed multiple moves, the dominant structural intent determined classification. Persistence audit excluded incomplete threads.

**Scoring rubric.** Output quality measured on a 20-point rubric against single-shot baselines: Relevance (30%), Completeness (20%), Actionability (10%), Signal Density (40%). Signal density carries the highest weight because it is the most reliable proxy for whether the output was actually used.

**Bias acknowledgment.** This is self-assessed, single-practitioner research. Confirmation bias is a genuine concern. The mechanical taxonomy is the part of this work most independent of subjective assessment — move definitions do not depend on whether the outcome scores are accurate. The performance deltas do.

---

## 7. Results

| Metric | Delta | n | Source |
|---|---|---|---|
| Composite outcome quality | +34% | 441 threads | Practitioner dataset |
| Signal density | +42% | 441 threads | Practitioner dataset |
| Objective fulfillment rate | +31% | 441 threads | Practitioner dataset |
| Code optimization success | 27.3% → 36.0% | External | Madaan et al., 2023 |
| Mathematical reasoning | 22.1% → 59.0% | External | Madaan et al., 2023 |
| Complex constraint satisfaction | 4.4% → 61.3% | External | Madaan et al., 2023 |

The three highest-impact moves by effect size in the practitioner dataset:

**Meta (+9.2 points average).** Largest single-move effect. Meta prevents goal displacement — when the session drifts from the stated goal to a different goal without explicit redirection. Its effect is disproportionate because it operates on the goal rather than the output. An incorrect goal with excellent execution produces an excellent answer to the wrong question.

**Decompose (+7.8 points).** On complex tasks, decomposition consistently prevented the "shallow everything" failure — where a single-shot prompt produces a complete-looking output with inadequate depth in every component. Isolating each sub-problem ensures full attention on each component sequentially.

**Refine (+6.1 points, conditional).** The effect size depends entirely on specificity. Open-ended refinement requests produced modest improvement. Refinement with an explicit quality bar — cut by 30%, back every claim with a mechanism, remove hedges — produced the observed delta.

---

## 8. Discussion

The +34% composite improvement reflects the difference between a model operating in an uncontrolled open loop and a model operating within a feedback loop that forces re-anchoring at defined intervals. The model is the same in both conditions. The architecture around it is not.

This reframes what model capability means in practice. If the same model, given the same task, produces results 34% better within a structured loop, then a large fraction of what practitioners attribute to model capability is attributable to interaction structure. Capability ceiling and structural ceiling are different things. Current practice regularly hits the structural ceiling while leaving the capability ceiling untouched.

A more capable model running an unstructured session produces more convincing drift — output that is wrong with higher fluency and more confident presentation. Improving the model without improving the structure around it produces higher-quality failure. The discipline of steering is not a workaround for current model limitations. It is the permanent requirement for reliable operation of any system powerful enough to drift without guidance.

What the study cannot address: multi-user generalizability, performance variation across model generations, or whether the improvement is attributable to the specific moves versus the general act of structuring any interaction. The control condition — structured interaction with a different vocabulary — was not tested. These are the appropriate targets for future multi-practitioner controlled study.

---

## 9. Conclusion

Output quality in language model interactions is not primarily a function of model capability. It is a function of the structure built around model execution.

The 13 steering moves formalize the operations that constitute that structure. Each one exists because a specific class of failure is predictable and recurring: premature commitment, scope expansion, instruction decay, constraint absence, goal displacement. Naming the moves makes the failures diagnosable. Diagnosable failures are correctable. Opaque failures are not.

The practitioner's choice is straightforward: run trial and error inside a black box and accept statistically average outputs, or build the architectural scaffold that surfaces the model's actual capability. The capability was always there. The structure is what makes it accessible.

The next step is not reading further. It is applying one move deliberately on the next task, evaluating whether it produced the expected structural effect, and adjusting from there.

---

## 10. References

Madaan, A., Tandon, N., Gupta, P., Hallinan, S., Gao, L., Wiegreffe, S., Alon, U., Dziri, N., Prabhumoye, S., Yang, Y., Welleck, S., Majumder, B. P., Gupta, S., Yazdanbakhsh, A., & Clark, P. (2023). SELF-REFINE: Iterative refinement with self-feedback. *Advances in Neural Information Processing Systems (NeurIPS)*, 36. https://arxiv.org/abs/2303.17651

Wei, J., Wang, X., Schuurmans, D., Bosma, M., Ichter, B., Xia, F., Chi, E., Le, Q., & Zhou, D. (2022). Chain-of-thought prompting elicits reasoning in large language models. *Advances in Neural Information Processing Systems (NeurIPS)*, 35. https://arxiv.org/abs/2201.11903

Yao, S., Yu, D., Zhao, J., Shafran, I., Griffiths, T., Cao, Y., & Narasimhan, K. (2023). Tree of thoughts: Deliberate problem solving with large language models. *Advances in Neural Information Processing Systems (NeurIPS)*, 36. https://arxiv.org/abs/2305.10601

Zhou, D., Scharli, N., Hou, L., Wei, J., Scales, N., Wang, X., Schuurmans, D., Cui, C., Bousquet, O., Le, Q., & Chi, E. (2022). Least-to-most prompting enables complex reasoning in large language models. *arXiv preprint arXiv:2205.10625*. https://arxiv.org/abs/2205.10625

White, J., Fu, Q., Hays, S., Sandborn, M., Olea, C., Gilbert, H., Elnashar, A., Spencer-Smith, J., & Schmidt, D. C. (2023). A prompt pattern catalog to enhance prompt engineering with ChatGPT. *arXiv preprint arXiv:2302.11382*. https://arxiv.org/abs/2302.11382

Schulhoff, S., Ilie, M., Balepur, N., et al. (2024). The prompt report: A systematic survey of prompting techniques. *arXiv preprint arXiv:2406.06608*. https://arxiv.org/abs/2406.06608

Anthropic. (2024). Building effective agents. *Anthropic Research*. https://www.anthropic.com/research/building-effective-agents
