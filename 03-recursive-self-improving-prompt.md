# The Recursive Self-Improving Prompt

The 13 steering moves exist because single-shot prompting collapses the entire problem—exploration, structure, constraints, and output—into one unguided request. The Core Loop solves that for multi-turn human-driven steering.

But there is a further problem: the human is a bottleneck.

Each move in the loop requires you to read the output, diagnose the failure mode, select the correct steering move, write the corrective prompt, and send it. That overhead is acceptable when you can see the output clearly. It becomes impractical when tasks are long, complex, or when you are not yet sure what failure you are trying to prevent.

The Recursive Self-Improving Prompt delegates the architectural work to the model itself. Instead of you selecting which move to apply, you instruct the model to analyze its own goal, identify where it will fail, and construct a high-fidelity prompt for itself—then execute that prompt.

This is not shorthand or convenience. It is a structural difference. When a model writes its own optimized instruction set, it identifies the precise phrasings that activate its own internal attention patterns most reliably. Abandoning a self-generated plan in the middle of execution has a higher probabilistic cost than abandoning a user's instruction. The model's own context anchors it.

---

## Why Self-Generated Prompts Are More Durable

Standard prompting: user writes instructions → model interprets and executes → context drifts as conversation extends.

Recursive self-prompting: model identifies its own ambiguities → writes its own execution plan → executes against anchored self-written constraints.

The key mechanism is this: a model that has written down its own constraints is less likely to violate them. The constraint enters the context window as something the model produced, not something imposed from outside. This is why academic implementations of this architecture (most prominently the SELF-REFINE framework) require no additional training data or reinforcement learning. The improvement comes entirely from the structural loop, not from changed weights.

The model plays three roles simultaneously:

- **Generator**: produces an initial draft or response
- **Critic**: evaluates that output and identifies specific, actionable failure modes
- **Refiner**: rewrites the previous output using its own critique as input

Each cycle tightens the output. The generator produces. The critic identifies what is weak, imprecise, or missing. The refiner fixes exactly those things. Because the feedback is self-generated and specific rather than generic and external, the refinement is targeted rather than cosmetic.

---

## What Changes in Output Quality

These are not subjective impressions. Measured across controlled studies:

| Metric                                              | Result        |
| --------------------------------------------------- | ------------- |
| Outcome quality (subjective, 441 threads)           | +34%          |
| Signal density (usable content vs. filler)          | +42%          |
| Objective fulfillment rate                          | +31%          |
| Absolute task performance (avg across 7 task types) | +20%          |
| Code optimization success (GPT-4)                   | 27.3% → 36.0% |
| Mathematical reasoning solve rate                   | 22.1% → 59.0% |
| Complex constraint satisfaction (20–30 constraints) | 4.4% → 61.3%  |

The math and constraint results are the most instructive. They do not represent a model that became smarter. They represent a model that was given a structured opportunity to catch its own mistakes before presenting a final answer. The capability was always there. The structure surfaces it.

> **Core insight:** High-quality output is not primarily an emergent property of model size or weights. It is an emergent consequence of the structural scaffolding built around the model's execution.

---

## Two Templates

### Template 1: The Master Recursive Formula

Use this when you want the model to fully architect and execute a complex task with no back-and-forth. You hand it a goal and an instruction to self-optimize before proceeding.

---

**GOAL:** `[INSERT YOUR OBJECTIVE HERE]`

**(META):** Do not execute the goal yet. Act as a Senior Prompt Architect. Your objective is to design a high-fidelity, recursive instruction set for yourself to achieve the goal above without stochastic decay.

**PROTOCOL:**

1. **(PROBE):** Analyze the goal for three semantic ambiguities or logic gaps that could lead to drift.
2. **(DECOMPOSE):** Break the task into a deterministic sequence of sub-problems where each output is fed as the input for the next (Least-to-Most architecture).
3. **(ADD CONSTRAINTS):** Specify the precise cognitive scaffolding required. Exclude all generic AI filler and establish strict formatting parameters.
4. **(ROLE SHIFT):** Integrate a Skeptical Critic layer to verify the internal logic of this prompt before execution.

**(RECURSE):** Once you have architected this optimized self-improving prompt, execute it immediately and provide only the final, high-signal result.

---

**What each instruction does:**

- **META pause**: The model is forbidden from executing immediately. This forces the architectural phase to happen separately from the production phase—exactly the same principle as Probe before Scope Tighten. You get a plan before content.
- **PROBE on its own goal**: The model identifies ambiguities in the goal _before_ attempting it. These are the drift points that would cause silent failure in a single-shot prompt.
- **DECOMPOSE as Least-to-Most**: Each sub-problem's output becomes the input for the next. No sub-problem is attempted without the prior one being resolved. This eliminates the "write everything at once and hope it's consistent" failure mode.
- **ADD CONSTRAINTS on its own reasoning**: The model defines what counts as acceptable output before producing it—format, scope, signal quality, what to exclude. This functions as self-applied cognitive scaffolding.
- **ROLE SHIFT to Skeptical Critic**: Before execution, the model's own critic layer reviews the prompt it just wrote. It is forced to find its weakest assumptions before they become output.
- **RECURSE to execute**: The architectural phase concludes and the model runs against its own specification. The result is produced against self-written, self-reviewed constraints.

---

### Template 2: The Convergent Recursive Loop

Use this for extended work where you want iterative progress with built-in navigation. The model both advances the task and tells you the exact next prompt to send—eliminating the bottleneck of you writing the steering prompts.

---

**GOAL:** `[INSERT YOUR OBJECTIVE HERE]`

**At each step, you will:**

**(A) PROGRESS:** Provide the best possible advance toward the goal given what has been established so far.

**(B) NEXT PROMPT:** Append a single follow-up prompt that the user should send next to advance the task most efficiently. Write this as a prompt, not a description of what the prompt should do.

**(C) CONVERGE:** Evaluate how close the work is to the finished goal. If convergence is not yet reached, proceed to the next cycle. If it is reached, state so explicitly and stop.

---

**What each instruction does:**

- **PROGRESS** grounds each response in concrete advancement. The model cannot pad with caveats or meta-commentary without violating its own constraint to produce the best possible advance.
- **NEXT PROMPT** is the operationally interesting instruction. The model is predicting which steering move it needs next and doing the prompt engineering work for you. This is self-directed loop management.
- **CONVERGE** prevents infinite loops. The model must evaluate its own progress against the original goal and declare done when done. This is a Meta move built into every cycle.

---

## Choosing Between the Templates

|                                   | Master Recursive Formula                                                 | Convergent Recursive Loop                                                 |
| --------------------------------- | ------------------------------------------------------------------------ | ------------------------------------------------------------------------- |
| **Best for**                      | Complex single-shot tasks where you want the full result in one response | Multi-turn work where you expect several cycles                           |
| **Human involvement**             | Minimal — you send one prompt and receive a fully executed result        | Low — you paste the model's own next-prompt each cycle                    |
| **Control**                       | Model controls architecture and execution                                | You can redirect between cycles                                           |
| **Risk**                          | Output depends entirely on the model's self-critique quality             | Requires trust that the "next prompt" is actually moving toward your goal |
| **Good signal that it's working** | The PROBE section surfaces real ambiguities, not vague generalities      | The NEXT PROMPT feels like what you would have written yourself           |

---

## The SELF-REFINE Framework

The academic formalization of this pattern is SELF-REFINE (Madaan et al., 2023). The framework defines a discrete three-step mechanical loop requiring no additional training, fine-tuning, or reinforcement learning.

**Generate:** The model produces an initial output from the original prompt.

**Feedback:** The model is instructed to evaluate its own output and generate _specific_, _multi-aspect_, _actionable_ critiques. The critical word is actionable. Generic feedback ("this could be improved") produces generic revision. Targeted feedback ("this function uses a brute-force O(n²) loop where a hash lookupwould run in O(1)") produces targeted revision.

**Refine:** The model rewrites using its own feedback as explicit input. The feedback is not implied context—it is passed directly into the next prompt as structured input, preventing the model from ignoring it.

This cycle repeats until a stopping condition is met. The stopping condition can be instruction-based ("refine until no more actionable feedback exists"), turn-based ("run three cycles"), or convergence-based (the model evaluates that its output has met the original spec).

---

## Where This Sits in the Larger Framework

The Master Recursive Formula and the Convergent Recursive Loop are not replacements for the 13 steering moves. They are meta-patterns that _use_ the 13 moves internally.

When the model runs the Master Recursive Formula and reaches the PROBE step, it is executing the Probe move. When it reaches ADD CONSTRAINTS, it is executing Add Constraints. The 13 moves become the vocabulary that the model uses to reason about its own execution.

This is the full architecture:

```
13 Moves          → manual steering tools for human-driven loops
Core Loop         → the default three-move sequence: Probe → Scope Tighten → Refine
Self-Improving    → model architects and audits its own instruction set using the moves above
```

Each layer assumes the one below it. You cannot use the self-improving templates effectively without understanding what PROBE and DECOMPOSE and ADD CONSTRAINTS actually do mechanically. The templates are not magic wording—they are instructions that map to specific cognitive operations. Understanding the operations is what lets you verify the model is executing them correctly rather than producing plausible-sounding output that collapses on inspection.
