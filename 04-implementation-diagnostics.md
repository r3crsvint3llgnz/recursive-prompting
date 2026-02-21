# Implementation, Diagnostics, and Checklists

The framework only functions if you can recognize when it is failing. A model that drifts quietly is more dangerous than one that produces obvious garbage—because quiet drift looks like success until you read closely or compare the output against your original intent.

This section is a diagnostic reference. For each common failure pattern, it names the symptom, identifies what is actually going wrong, and specifies which move to apply. At the end are three checklists for starting a session, mid-session evaluation, and recovering from collapse.

---

## Diagnostic Index: Failure Patterns and Corrective Moves

### Pattern 1 — Generic Output

**Symptom:** The model produces correct, competent text that could have been written for anyone. Nothing in the output is specific to your context, constraints, or audience.

**What is happening:** The model defaulted to its training distribution. Without explicit constraints forcing specificity, it outputs the statistically average response for the type of request. This is not hallucination. It is competent mediocrity.

**Corrective moves, in order:**

1. **Add Constraints** — define what the output must contain, must exclude, and must conform to. Generic output is almost always a constraints problem. Adding three or four sharp constraints is usually sufficient.
2. **Seed** — return to the start and re-establish context. If the model does not have enough specific input material, it cannot produce specific output. Supply what is missing.
3. **Role Shift** — specify a concrete audience or evaluator. "Explain this to a skeptical CTO who has already seen three failed implementations" forces specificity that "explain this clearly" does not.

---

### Pattern 2 — Scope Creep / Tangential Output

**Symptom:** The model includes material you did not ask for. It expands beyond the stated task, adds caveats, qualifications, section headers for unstated sections, or content that belongs to a different part of the work.

**What is happening:** Without an explicit scope boundary, the model fills adjacent space. It is not wrong about the tangential content—it is wrong about what was asked.

**Corrective moves, in order:**

1. **Scope Tighten** — state the exact boundaries. "Focus only on X. Do not address Y or Z." Be explicit about exclusions, not just inclusions.
2. **Format Control** — specify the exact output structure. A model that knows it must produce exactly five bullet points cannot also produce seven.
3. **Decompose** — if the task is large, break it into discrete steps and request each one individually. Scope creep is common when large tasks are executed in a single shot.

---

### Pattern 3 — Premature Commitment

**Symptom:** The model presents one option as though it is the obvious choice before you have evaluated alternatives. The first response is presented with confidence, and subsequent responses optimize from that starting point rather than reconsidering it.

**What is happening:** The model anchored on the first plausible interpretation of your request. All subsequent outputs are refinements of that anchor, not independent evaluations.

**Corrective moves, in order:**

1. **Probe** — explicitly request multiple distinct alternatives. "Give me five approaches with different underlying assumptions." The key word is _different_—the model will produce variations on the same idea unless forced to diverge.
2. **Compare** — once alternatives exist, force an explicit evaluation. "Compare these on X, Y, and Z criteria." This prevents the original anchor from quietly reasserting itself.
3. **Meta** — if you are deep into a session and suspect you are optimizing the wrong thing, step back. "Pause. What is the actual goal here, and is this approach the right one?"

---

### Pattern 4 — Shallow Depth / Surface-Level Output

**Symptom:** The model produces technically correct content that lacks the density, specificity, or depth expected. Headers and bullet points are present but the content under them is thin. Claims are made without support. Examples are generic.

**What is happening:** The model completed the requested structure without completing the requested substance. Structural compliance is easier than substantive depth, so the model executes structure first.

**Corrective moves, in order:**

1. **Recurse** — select the specific weak section and request targeted expansion. "Expand only Section 2. Add supporting evidence, a concrete example, and practical implications." Do not ask it to "improve" the whole output—depth problems require targeted recursion.
2. **Refine** — specify the quality bar. "Refine this section: remove all generic statements, back every claim with a specific example or mechanism."
3. **Add Constraints** — for future sections, enforce density upfront. "Each bullet must include one concrete example and one failure condition. No generic advice."

---

### Pattern 5 — Hallucination / Fabricated Specifics

**Symptom:** The model produces outputs with confident, plausible-sounding details that are incorrect—wrong statistics, fabricated citations, invented examples, false attributions.

**What is happening:** The model filled specificity gaps with statistics plausible. This is a probability problem, not a deception problem. The model has no source; it generates what looks like a source.

**Corrective moves, in order:**

1. **Hypothesis** — reframe the specific claims as hypotheses requiring validation. "You stated X. Convert this to a testable hypothesis and identify what evidence would confirm or falsify it." This labels uncertainty correctly and gives you a validation target.
2. **Scope Tighten** — restrict to what the model can reason about without inventing. "Do not include statistics, citations, or examples unless they are clearly marked as illustrative placeholders."
3. **Meta** — audit what the model actually knows versus what it appears to know. "Which of the claims in this output are drawn from well-established information, and which are likely inferences or approximations?"

> **Operational note:** Hallucinations are not diagnosable from inside the model. Any corrective move here is risk reduction, not elimination. For factual outputs that will be published or acted on, human verification is not optional.

---

### Pattern 6 — Instruction Decay / Drift

**Symptom:** The model begins a long session following your instructions but gradually stops. Constraint violations reappear. Style reverts. Format rules are ignored. The output 10 exchanges in looks like single-shot output again.

**What is happening:** Context window compression. As conversations extend, earlier instructions lose attention weight. The model is not ignoring them—it is allocating attention proportionally, and early instructions become proportionally smaller.

**Corrective moves, in order:**

1. **Seed** — re-establish the full context explicitly. "This is a reset. The goal is [X]. The constraints are [Y]. The format is [Z]. Produce the next section with these specifications active." Treat it as a new session that inherits prior outputs.
2. **Meta** — force the model to audit its own drift. "Compare your last response against these original constraints: [paste constraints]. Flag every deviation." The model can often identify its own drift when forced to look directly at it.
3. **Recurse + Add Constraints** — take the last compliant output and recurse forward with constraints restated. Do not try to continue from the drifted state—return to the last good checkpoint.

---

### Pattern 7 — Goal Displacement

**Symptom:** The model produces content that optimizes for prompt satisfaction rather than actual goal completion. Outputs are well-structured, tonally appropriate, and plausibly correct—but they solve the problem of seeming complete rather than being complete.

**What is happening:** The model is rewarded in training for outputs that human raters rate positively. Positive ratings correlate with surface quality signals: structure, fluency, appropriate length, confident tone. These do not reliably correlate with task completion. You asked for a strategy; the model gave you a strategy-shaped object.

**Corrective moves, in order:**

1. **Role Shift + Hypothesis** — adopt an adversarial evaluator role. "As a skeptical critic: what assumptions in this strategy are untested? What is the most likely way this fails?" Forces the content past surface plausibility.
2. **Decompose** — break the goal into verifiable sub-deliverables. If you cannot state what "done" looks like for each component, the model cannot produce it reliably.
3. **Meta** — directly name the problem. "Step back from this output. Does it actually answer [original goal], or does it demonstrate that it answered [original goal]? Be specific about the difference."

---

### Pattern 8 — Circular Refinement

**Symptom:** You apply Refine repeatedly but the output is not improving. Each version is slightly different but not meaningfully better. The model produces variations rather than improvements.

**What is happening:** Refine without a specific directive produces stylistic variation, not substantive improvement. The model cannot improve against a standard it has not been given.

**Corrective moves, in order:**

1. **Hypothesis** — name the specific failure the refinement is trying to fix. "This output fails because [X]. Refine specifically to address [X]." Vague refinement requests produce vague improvements.
2. **Compare** — produce two or three refinement candidates with different approaches and compare them explicitly. This reveals whether there is a genuinely better direction or whether the outputs have converged.
3. **Scope Tighten + Add Constraints** — set a precise quality bar before refining. "Refine this paragraph: it must be ≤80 words, must contain one specific mechanism, and must begin with the key claim." This makes improvement measurable.

---

## Warning Signs: Early Indicators to Act On Immediately

These are not failure patterns yet—they are leading indicators. When you see them, apply a corrective move before the problem deepens.

**The affirmative preamble.** The model opens its response with "Great question!" or "Absolutely!" or a summary of what you just asked. This is a signal that the model is producing high-rated-seeming output rather than directly executing. Apply **Format Control** or **Add Constraints** to cut the preamble immediately and preempt the pattern in future responses.

**The caveat cascade.** Multiple paragraphs beginning with "However,", "It's important to note,", "That said,". This is hedge inflation—the model protecting itself from being wrong by qualifying everything. Apply **Scope Tighten** or **Add Constraints** ("state claims directly; do not hedge unless the uncertainty is operationally significant").

**The list that shouldn't be a list.** Complex causal reasoning broken into bullet points where each bullet is a sentence. Lists work for discrete, parallel items. When the model converts sequential reasoning into bullets, it is destroying the logical connective tissue. Apply **Format Control** to demand prose where the ideas are connected.

**The non-answer answer.** You ask a direct question; the model gives context, background, and framing, but never directly states the answer. Apply **Scope Tighten** + **Meta**: "Answer only the specific question I asked. One paragraph maximum. Then stop."

**The symmetrical conclusion.** The output ends with a conclusion that acknowledges "both sides have merit" or "it depends on your specific situation." This is a trained-to-be-safe conclusion that adds no information. Apply **Role Shift** + **Hypothesis**: "Take a position. State the most defensible answer and explain why. Qualify only where the qualification is operationally significant."

**Length inflation.** The response is longer than you expected without being more useful. Signal density has dropped. Apply **Refine** with: "Cut this by [X]%. Preserve every claim that has specific supporting content. Eliminate everything else."

---

## Session Checklists

### Checklist 1 — Before Starting a Session

Use before any complex task. These are the inputs the model needs to produce high-signal output.

- [ ] Goal is stated as a specific deliverable, not a subject area
- [ ] Success criteria defined: what does "done" look like?
- [ ] Output format specified: length, structure, what to include and exclude
- [ ] Role or audience identified if the output is for a specific reader
- [ ] Constraints stated: tone, scope limits, what not to include
- [ ] Is this a single-shot task or multi-turn? If multi-turn: plan the move sequence before starting.
- [ ] For complex/long tasks: consider using the Master Recursive Formula instead of manual steering

---

### Checklist 2 — Mid-Session Evaluation (every 3–5 exchanges)

Use to catch drift before it compounds.

- [ ] Is the output still addressing the original goal, or has it shifted?
- [ ] Are the constraints from the original Seed still being honored?
- [ ] Have format requirements been maintained?
- [ ] Is the signal density still high, or has inflation crept in?
- [ ] Is the model introducing assumptions you did not provide?
- [ ] Does the last response feel like progress toward the deliverable, or motion without movement?

If any of these fail: **Seed**. Reset context explicitly. Do not continue from a drifted state.

---

### Checklist 3 — When Recovery Is Needed

Use when a session has clearly gone wrong—multiple failed attempts, circular output, or results that do not match the original goal.

- [ ] **Stop refining the current output.** Continuing a failed thread compounds the problem.
- [ ] Return to the most recent output you judged acceptable (or start fresh).
- [ ] Re-state the goal from scratch, as if the model has no context.
- [ ] Apply **Decompose** — break the original task into sub-steps, start with the first one only.
- [ ] If the failure mode was hallucination or fabrication: apply **Hypothesis** + **Scope Tighten**, restrict to what the model can reason about reliably.
- [ ] If the failure mode was scope creep or tangential content: apply **Scope Tighten** + **Format Control** with explicit exclusion list.
- [ ] If the failure mode was generic or thin output: apply **Add Constraints** + **Recurse**, targeting the specific thin section.
- [ ] If the goal itself is unclear: apply **Meta** before any other move.

---

## Move Selection Quick Reference

| Symptom                             | Primary Move             | Supporting Move          |
| ----------------------------------- | ------------------------ | ------------------------ |
| Output could apply to anyone        | Add Constraints          | Seed                     |
| Model went outside the task         | Scope Tighten            | Format Control           |
| Stuck on first idea                 | Probe                    | Compare                  |
| Output is shallow or thin           | Recurse                  | Refine + Add Constraints |
| Confident but wrong specifics       | Hypothesis               | Scope Tighten            |
| Instructions fading over session    | Seed (reset)             | Meta                     |
| Completing form, not function       | Role Shift               | Decompose                |
| Refinement spinning in place        | Hypothesis               | Compare                  |
| Affirmative preamble / hedges       | Add Constraints          | Format Control           |
| "Balanced" conclusion adds nothing  | Role Shift               | Hypothesis               |
| Goal is unclear to you              | Meta                     | Decompose                |
| Task is too large to steer manually | Master Recursive Formula | —                        |

---

## On the Limits of Corrective Steering

The moves in this section are responsive—they fix problems that have already appeared. The more reliable approach is preventive: using **Seed**, **Add Constraints**, and **Decompose** at the start of a session eliminates most of the failure patterns above before they occur.

Responsive steering is not a substitute for architecture. A session that requires repeated corrective moves is a session that needed better initial structure. The pattern to internalize is: invest more in the first two or three prompts, and spend less time recovering later.

When a task is complex enough that you cannot confidently structure it in advance, that is the signal to use the **Master Recursive Formula** and let the model's own architectural phase surface the gaps. The meta-prompt does not produce magic output—it produces a structured plan that you can evaluate before the execution phase begins, which is strictly better than discovering the plan was wrong mid-execution.
