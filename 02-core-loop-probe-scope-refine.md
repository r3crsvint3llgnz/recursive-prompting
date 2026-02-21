# The Core Loop: Probe → Scope Tighten → Refine

Recursive prompting is a unified framework for managing the probabilistic nature of LLMs through a systematic interaction pattern. The Probe → Scope Tighten → Refine loop replaces guessing with steering. Instead of collapsing the entire problem into a single request and accepting whatever the model produces, the loop breaks work into distinct stages, each with a clear purpose and a decision point.

This is not ornamental process. It is structural necessity. When you force the model to externalize its reasoning at each stage, you regain control over the direction before committing effort.

## Probe: Separate Exploration from Commitment

The Probe move prevents premature commitment. Its function is to reveal the model's solution space before you invest in the wrong direction.

In this stage, you are not asking the model to decide, write, or optimize. You are asking it to show you what options exist.

**What Probe does:**

- Forces the model to externalize multiple possible framings or approaches without deciding which one is correct
- Creates a visible decision point: you see the options before the model narrows them
- Keeps exploration cheap by constraining scope (e.g., "5 options, 1-sentence promise each") so all choices remain comparable

**Example:**

```
Give 5 angles for a leadership presentation on AI adoption in the company.
Each angle should include:
  - A 1-sentence promise (what does this frame deliver?)
  - Intended audience (who is this actually for?)

Do not write full content. Just show the angle and its purpose.
```

This constraint does critical work. "5 angles" surfaces real differences without overwhelming. "1-sentence promise" keeps each option comparable and reveals hidden assumptions. "Intended audience" exposes mismatches early—many apparent output quality problems are actually audience misalignment.

At the end of Probe, you should have clarity about which direction is promising, not finished content you want to keep.

## Scope Tighten: Make the Choice Explicit

Once you have explored options, the next move is to commit to a direction and ignore the rest.

In this stage, you are no longer exploring. You are telling the model what to focus on and what to exclude.

**What Scope Tighten does:**

- Commits to one specific direction by selecting it explicitly
- Prevents the model from blending multiple approaches together
- Separates structure from prose by asking for outline instead of full content
- Reduces work scope so you can evaluate direction before polishing

**Example:**

```
Pick angle #3 (Risk Mitigation and Governance).
Write only the outline with section headings and 2-3 bullet points per section.
Exclude benefits, timelines, and technical implementation details.
Show structure only. No full sentences.
```

The critical move here is "Exclude everything else." This is not decorative language. It prevents the model from being helpful in directions you have already decided to ignore. The model stops hedging and stays focused.

At this stage, you check whether the chosen direction holds up structurally. If the outline is wrong, you change the angle and try again (loop back to Probe). If it works, you move forward.

## Refine: Amplify Under Constraint

Once structure is sound, refinement amplifies the right direction using clear boundaries.

In this stage, the model is no longer deciding what to say. That work is done. Refinement tells the model _how_ to say it.

**What Refine does:**

- Operates within boundaries already established (angle chosen, structure approved)
- Removes ambiguity through concrete constraints (length, style, format, audience tone)
- Lets the model spend effort on execution instead of guessing
- Produces final output ready to use or quickly adjust

**Example:**

```
Rewrite the outline into final presentation copy.

Constraints:
  - 400–600 words
  - Short sentences (avoid subordinate clauses)
  - 4 sections max
  - End with 3 specific next actions: what, who, by when
  - Tone: urgent and grounded (not aspirational)
```

Constraints do not reduce quality. They improve it by removing the model's burden to guess. When the model knows the boundaries, it executes within them.

## Why This Loop Works: Process, Not Prompting

The difference between single-shot and recursive prompting is structural, not wording.

**Single-shot prompt:**

```
Write a short presentation for our leadership team about AI adoption.
```

The model must guess: What does leadership actually care about? Is this informative or persuasive? How technical? What belongs on slides? Because no decisions are explicit, the output spreads itself thin. Nothing is obviously wrong. Nothing is clearly right.

**Recursive approach:**
Same task, same model, different process.

The loop does three things:

1. **Stages the work** instead of collapsing it. Each step has a clear purpose.
2. **Makes decisions explicit** before action. You decide angle, structure, constraints—the model executes within them.
3. **Removes guessing** by controlling scope early. You evaluate direction cheaply (via outline) before polishing content you might throw away.

The model does not become smarter. The process becomes deterministic.

## Performance Impact Through Structural Constraint

### What Ontologies Mean (And Why Direct Prompting Fails)

An ontology is simply a **master list of what's real** in a specific field. Think of it like a periodic table of elements, a dictionary, or a phone book. It is the official reference that says: "These things exist. Those things don't."

Real-world examples:

- **Periodic Table**: The official list of all real chemical elements. Hydrogen is real. "Kryphtonium" is not.
- **Email Directory**: The actual list of valid email addresses in a company. If someone asks "who is john_smith@company.com?", you check the directory to see if that email actually exists.
- **Disease Database**: The official catalog of diagnosed diseases. "Influenza" is real and has a code. A made-up name like "Sneezeplague-7" is not.

In the AI world, similar reference lists exist for genes, diseases, and anatomical structures. Scientists use them to label and organize research data.

**Here's where LLMs fail without this reference:**

When you ask an LLM "What disease is this text describing?" without giving it a reference list, the model has to guess. And LLMs are exceptionally good at generating text that _sounds_ real—even if it's completely fabricated.

Direct LLM prompting fails because the model cannot distinguish between:

- **Real disease names**: "Duchenne muscular dystrophy" (a real, documented disease with a diagnosis code)
- **Plausible-sounding fabrications**: "Cellular opacity syndrome" (sounds technical, but doesn't actually exist and has no diagnosis code)

The LLM just picks whichever sounds good. It has no way to know which one is actually in the real disease database.

### How Recursive Extraction (SPIRES) Changes the Game

SPIRES (Structured Prompt Interrogation and Recursive Extraction of Semantics) applies the Probe → Scope Tighten → Refine pattern to ontology grounding:

1. **Probe**: Extract candidate entities from unstructured text
2. **Scope Tighten**: Map candidates against the known ontology (constraint structure)
3. **Refine**: Verify and reconcile ambiguous matches through repeated cycles

The loop does not ask the model to memorize Gene Ontology. It uses the ontology as an external constraint that the model must respect. At each iteration, the model is forced to choose from known entities, not invent them.

### The Performance Gap Is Structural, Not Incremental

| Task                         | With Structured Iteration | Direct LLM Prompting |
| ---------------------------- | ------------------------- | -------------------- |
| Gene Ontology grounding      | 98/100                    | 3/100                |
| Disease ontology (MONDO)     | 97/100                    | Inferior/N.A.        |
| Anatomical grounding (EMAPA) | 100/100                   | Inferior/N.A.        |

Direct prompting achieves 3/100 on Gene Ontology—worse than random guessing. Adding the same model with iterative extraction and constraint grounding achieves 98/100.

This is not about a better prompt or longer instructions. This is the model operating inside a constraint structure where:

- The search space is pre-defined (only valid ontology entries are acceptable)
- Hallucination space is eliminated (invalid fabrications are caught at the Scope Tighten stage)
- Verification is built in (each loop iteration validates against ground truth before proceeding)

The model did not improve. The process did.

### Scaling to Extreme Complexity: The MAKER Demonstration

But constraint-based iteration is not just for classification tasks. MAKER demonstrates that the loop scales to extreme task complexity.

MAKER is a system for long-form structured reasoning that uses verification loops at depth. The key finding: **one million dependent reasoning steps** become possible without error accumulation if each step is verified against established state.

Think about what "one million steps" means:

- Most LLMs begin to collapse in coherence around 50–100 steps of forward reasoning (as discussed in the introduction)
- One million steps would be impossible without catastrophic drift
- Yet with iterative verification at the loop level, it is achievable

This is not because the base model became better. It is because the architecture changed: instead of linear forward-chaining (which accumulates error), you now have cyclical verification (which resets error at each loop).

Each cycle:

1. **Probe**: Check current state
2. **Scope Tighten**: Commit to the next verified step
3. **Refine**: Apply constraints before proceeding

Repeat one million times. The loop prevents drift because at each iteration, the model is re-anchored to the last verified state. It cannot wander far because it must justify its next step against what already works.

### The Core Insight: Architecture Over Capacity

This is the threshold insight for the entire framework:

**Reliability does not come from larger models. It comes from better control structures.**

A language model with 7 billion parameters running in a constraint loop outperforms a 70 billion parameter model running one-shot. The difference is not the models—it is the interaction pattern.

When you apply recursive prompting:

- You transform a **stochastic generator** into a **controlled executor**
- You replace **guessing at scale** with **verification at scale**
- You turn **model capacity** into **process discipline**

This is why iterative steering becomes mandatory as stakes rise. It is not optional optimization. It is the only architecture that survives contact with complexity.

## The Reusable Sequence

This loop works because it is universal. The stages stay constant. Only content changes.

**Baseline** → State the task, audience, and topic. Context without decision.

**Probe** → Ask for multiple options or framings. Explore the solution space without committing.

**Scope Tighten** → Choose one direction. Show structure at no cost (outline, not draft). Evaluate before polishing.

**Refine** → Apply constraints. Produce final output. The model executes, not decides.

## The 13 Atomic Steering Moves

The core loop (Baseline → Probe → Scope Tighten → Refine) is the engine. The 13 steering moves are the controls.

You do not need all 13 moves every time. Most tasks use 4–6 moves in sequence. But knowing all 13 gives you a menu of actions when quality drops, scope drifts, or output gets vague.

### Group 1: The Scouts (Exploration)

These moves help you explore before committing.

1. **Probe** — Generate multiple directions before choosing one.
2. **Compare** — Rank options using explicit criteria (e.g., speed, risk, clarity).
3. **Hypothesis** — State your assumption and test what would disprove it.

**Pattern:** explore → rank → test assumptions.

### Group 2: The Lenses (Boundaries)

These moves control scope and prevent drift.

4. **Scope Tighten** — Narrow to one direction and exclude everything else.
5. **Scope Loosen** — Zoom out to check system-level fit (team, timeline, downstream impact).
6. **Add Constraints** — Force operational limits (length, format, tone, forbidden elements).

**Pattern:** narrow when output is noisy, loosen when output is too local.

### Group 3: The Blueprints (Construction)

These moves structure the build.

7. **Seed** — Set initial state (goal, audience, success criteria) so the model does not guess context.
8. **Decompose** — Break one large task into ordered sub-steps.
9. **Format Control** — Specify output shape (table, checklist, outline, JSON schema).

**Pattern:** define context → split task → enforce structure.

### Group 4: The Command Layer (Polish and Meta-Control)

These moves improve quality and prevent hidden errors.

10. **Refine** — Improve clarity, precision, and usefulness under fixed constraints.
11. **Role Shift** — Re-run output from a different evaluator perspective (skeptic, editor, architect, reviewer).
12. **Meta** — Pause and ask: “What question are we actually answering?”
13. **Recurse** — Re-apply the loop to a sub-part instead of rewriting everything.

**Pattern:** polish → challenge → realign → deepen.

## Why Multi-Turn Prompting Breaks (And How the 13 Moves Fix It)

Most beginners notice the same pattern.

You start a conversation and the first few responses are sharp. Then the thread gets longer, broader, and less useful. The model starts connecting topics you never asked it to connect. It agrees with contradictions. It sounds coherent, but stops answering your actual question.

That is **semantic drift**.

Here is the mechanism in plain terms: the model does not reason from a fixed end-goal. It predicts the next token from the recent context. If one turn introduces a small error or tangent, later turns build on that error. Without a reset, conversations accumulate noise.

Think of it like building a wall:

- One slightly misplaced brick seems harmless
- Every layer after that leans a little more
- Eventually the wall is still standing, but no longer straight

This is why “one better prompt” is not enough in long threads. You need **structural intervention**: deliberate moves that pause, separate perspectives, and re-anchor the conversation.

## The Control Trio for Multi-Turn Work

In multi-turn workflows, three moves become non-negotiable:

- **Role Shift** separates perspectives so they do not blend
- **Meta** checks alignment before drift compounds
- **Compare** evaluates options side-by-side without averaging them into one mushy answer

Use them as a package when the task includes trade-offs, conflicting goals, or multiple stakeholders.

### Role Shift: Separate Perspectives Before They Blend

Role Shift forces the model to answer from one frame only.

Without Role Shift, the model averages across everything in context: your original request, counterarguments, edits, tone changes, and implied goals. Output becomes polite but blurry.

With Role Shift, you specify a single lens:

"Take the role of a skeptical reviewer who thinks this plan will fail. What specific assumptions break first?"

Now the model is not trying to be balanced and helpful at the same time. It is operating inside one frame.

#### Two ways to use Role Shift

1. **Preventive Role Shift (exploration)**

- Use before committing to a decision
- Goal: collect distinct viewpoints (skeptic, user, expert, stakeholder)

2. **Corrective Role Shift (repair)**

- Use after the thread gets mushy
- Prompt: "Ignore prior framing. Answer from scratch as [role] under these constraints..."
- Goal: break out of blended context and reset

### Meta: Pause and Verify the Real Question

Meta is your circuit breaker.

Use it when responses are still “good” but feel subtly off-target.

Prompt:
"Before continuing, state the exact question we are trying to answer, what constraints we are honoring, and what has drifted."

Meta prevents spending 20 more turns polishing the wrong problem.

### Compare: Keep Trade-Offs Visible

After Role Shift, you will have multiple perspectives. Do not ask for a blended synthesis too early.

Use Compare to keep options separate and explicit.

Prompt:
"Compare the Skeptic, End User, and Domain Expert viewpoints in a table. Score each on risk, speed, cost, and reversibility. Do not merge them."

Compare gives you decision clarity without collapsing differences.

## The Four Core Role Patterns (Beginner Version)

If you only use four roles, use these:

1. **Skeptical Reviewer** — Finds hidden flaws and weak assumptions
2. **End User** — Finds friction, confusion, and missing steps
3. **Domain Expert** — Adds technical depth and best practices
4. **Stakeholder with different priorities** (CFO, compliance, privacy) — Exposes conflicts you are not optimizing for

Each role is a filter. You are not asking the model to “be smarter.” You are asking it to look through a different lens.

## 10-Minute Practice Drill (So This Becomes Habit)

Pick one real output you produced today (email, plan, summary, decision memo).

Run this sequence:

1. "As a skeptical reviewer, what are the top 3 failure points?"
2. "As the end user, where will this be confusing or frustrating?"
3. "As [stakeholder], what objections would block approval?"
4. "Compare all three perspectives in a table. Keep them separate."
5. "Refine the original output using only high-impact fixes that appear in at least two perspectives."

If the three role outputs look too similar, your roles are too vague. Tighten the role prompt and run again.

## Failure Pattern to Watch For

If your thread starts feeling "mushy," check for blended constraints.

Example:

- "Keep it brief and polite"
- "Now be more assertive"
- "Now add warmth"

These can conflict in one draft. The model tries to satisfy all at once and outputs a hedged average.

Fix:

1. Role Shift into one priority at a time
2. Compare outputs side-by-side
3. Scope Tighten to one direction
4. Refine under explicit constraints

This is the operational difference between chatting with an LLM and steering it.

## Repeatable Patterns by Use Case

The value of the 13 moves is not memorization. It is reuse. Below are reliable move sequences you can run across common tasks.

### 1) Writing and Communication

**Goal:** produce targeted writing without generic filler.

**Sequence:**
`Seed → Probe → Compare → Scope Tighten → Format Control → Refine`

**Example prompt chain:**

1. _Seed:_ “Audience: executive team. Goal: decision, not education. Success = clear recommendation and 3 actions.”
2. _Probe:_ “Give 5 angles for this message.”
3. _Compare:_ “Rank the 5 angles by urgency and business impact.”
4. _Scope Tighten:_ “Use angle #2 only. Exclude all others.”
5. _Format Control:_ “Output as: opening, 3 key points, risks, 3 actions.”
6. _Refine:_ “Rewrite for short sentences and decisive tone.”

### 2) Coding and Technical Implementation

**Goal:** avoid jumping into code before architecture is stable.

**Sequence:**
`Seed → Probe → Decompose → Scope Tighten → Add Constraints → Refine → Role Shift`

**Example prompt chain:**

1. _Seed:_ “Build a feature with reliability > speed. Must be testable and maintainable.”
2. _Probe:_ “List 4 implementation approaches with tradeoffs.”
3. _Decompose:_ “Break the selected approach into 6 ordered tasks.”
4. _Scope Tighten:_ “Implement task 1 only. Do not touch unrelated modules.”
5. _Add Constraints:_ “No new dependencies. Keep public API unchanged.”
6. _Refine:_ “Simplify complexity and remove redundant logic.”
7. _Role Shift:_ “Review this as a strict code reviewer. Find failure modes.”

### 3) Research and Analysis

**Goal:** prevent shallow synthesis and unsupported claims.

**Sequence:**
`Seed → Probe → Hypothesis → Compare → Scope Tighten → Format Control → Meta`

**Example prompt chain:**

1. _Seed:_ “Question: why method A fails under long contexts. Audience: technical reader.”
2. _Probe:_ “Give 4 explanatory frames for this failure.”
3. _Hypothesis:_ “State the main hypothesis and what evidence would falsify it.”
4. _Compare:_ “Compare frame strength against available evidence.”
5. _Scope Tighten:_ “Proceed with the strongest frame only.”
6. _Format Control:_ “Output: claim, mechanism, evidence, limitation, implication.”
7. _Meta:_ “Are we answering the original question or drifting into adjacent topics?”

### 4) Decision Support and Planning

**Goal:** create actionable plans instead of vague recommendations.

**Sequence:**
`Seed → Probe → Scope Loosen → Compare → Scope Tighten → Decompose → Refine`

**Example prompt chain:**

1. _Seed:_ “Decision: choose rollout strategy. Constraint: 8-week timeline.”
2. _Probe:_ “Generate 3 possible strategies.”
3. _Scope Loosen:_ “Evaluate organizational impact across teams.”
4. _Compare:_ “Score options by risk, cost, and reversibility.”
5. _Scope Tighten:_ “Select one strategy and exclude alternatives.”
6. _Decompose:_ “Convert to weekly execution steps with owners.”
7. _Refine:_ “Make steps concrete and measurable.”

## How to Use This Practically

Start with this default stack for most tasks:

`Seed → Probe → Scope Tighten → Format Control → Refine`

Then add moves only when needed:

- Add **Compare** when options feel equivalent
- Add **Hypothesis** when reasoning feels untested
- Add **Role Shift** when quality seems good but fragile
- Add **Meta** when the conversation drifts
- Add **Recurse** when one section is weak but the whole draft is strong

The goal is not to run all 13 moves. The goal is to pick the right move at the right failure point.

## When This Matters Most

The loop pays off immediately in high-stakes contexts where wrong direction costs time:

- **Strategic writing**: Probe for angles, tighten to one argument, refine into final position
- **Code generation**: Probe for architectural approaches, tighten to one pattern, refine into final implementation
- **Research synthesis**: Probe for interpretive frames, tighten to one narrative, refine into coherent argument
- **Decision support**: Probe for decision criteria, tighten to relevant factors, refine into clear yes/no framework

The pattern is reusable. Once you learn the sequence, you can apply it to any task where you currently ask the model to guess.

## The Shift in Responsibility

The critical move is this: you stop asking the model to make decisions you have not made yet.

Instead of "write something good about AI adoption" (let the model decide what good means), you guide it through: "here are possible angles → pick this one → here is how I want it structured → here is the final style."

Control is not about finding the perfect wording. It is about breaking work into steps you can see, inspect, and adjust before the next step.

This is the difference between prompting and steering. Prompting is one-directional (you send input, model responds). Steering is cyclical (you explore, commit, refine). In a probabilistic system, steering is not optional—it is the only path to reliability.
