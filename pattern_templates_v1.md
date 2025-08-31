# Recursive Prompting Pattern Templates (v1)

## Seed → Probe → RoleShift

**ID**: sequence_seed_probe_roleshift

**Difficulty**: intermediate

**Moves**: Seed, Probe, RoleShift

**Description**: I set context, explore options, then switch perspective to stress-test my direction.

**Use Cases**: personal planning, team decision pre‑read, study strategy options

**Example Prompts:**
- Here’s my goal and constraints: [goal/constraints].
- Give me 5 different approaches, each with 1–2 pros and cons.
- Now evaluate the approaches as a skeptical reviewer and call out risks I’m missing.

**Template:**

**Step 1 — Seed (establish the task)**: State the goal, constraints, and success criteria in one compact brief.
**Step 2 — Probe (generate alternatives)**: Ask for multiple approaches with quick trade‑offs.
**Step 3 — RoleShift (stress‑test)**: Switch the model into a role (skeptic, domain expert, user) to surface blind spots.

**When I use it**: Early in planning when I want breadth first, then a reality check.

**Note from my practice**: In my sessions, the perspective shift reliably exposes hidden constraints before I commit.


---

## Probe → ScopeTighten → Refine

**ID**: sequence_probe_scopetighten_refine

**Difficulty**: beginner

**Moves**: Probe, ScopeTighten, Refine

**Description**: I start broad, narrow to the strongest thread, then polish it.

**Use Cases**: one‑pager drafting, feature cut‑down, study notes distillation

**Example Prompts:**
- Brainstorm 6 options; keep them concise.
- Focus only on the option with the best effort/impact ratio and expand it.
- Refine the draft to be clearer and more actionable; remove filler.

**Template:**

**Step 1 — Probe (diverge)**: Generate several options.
**Step 2 — ScopeTighten (converge)**: Select one criterion (e.g., speed) and deepen only that path.
**Step 3 — Refine (polish)**: Improve clarity, concision, and actionability.

**When I use it**: To avoid bike‑shedding and get one good draft moving.

**Note from my practice**: Consciously switching from divergence to convergence cuts decision fatigue for me.


---

## ScopeTighten → ScopeLoosen → Recurse

**ID**: sequence_scopetighten_scopeloosen_recurse

**Difficulty**: intermediate

**Moves**: ScopeTighten, ScopeLoosen, Recurse

**Description**: I zoom in for specifics, zoom out to check fit, then iterate.

**Use Cases**: bug triage, policy changes, curriculum sequencing

**Example Prompts:**
- Detail only the error path for this API call.
- Zoom out: how does this affect the end‑to‑end user flow?
- Revise the fix plan to reflect both the low‑level details and the bigger impact.

**Template:**

**Step 1 — ScopeTighten**: Constrain to one slice of the problem.
**Step 2 — ScopeLoosen**: Re‑evaluate the wider context/impacts.
**Step 3 — Recurse**: Produce an improved synthesis.

**When I use it**: Systems work where local changes ripple globally.

**Note from my practice**: The deliberate zoom dance helps me avoid local optimizations that backfire later.


---

## Meta → Decompose → Seed

**ID**: sequence_meta_decompose_seed

**Difficulty**: beginner

**Moves**: Meta, Decompose, Seed

**Description**: I pause to reflect, break the problem into parts, then seed the first part precisely.

**Use Cases**: research planning, project kickoffs, study plans

**Example Prompts:**
- Quick check: what’s the actual question I’m trying to answer?
- Split this into 3–5 sub‑tasks with clear inputs/outputs.
- Seed sub‑task A: define inputs, desired output, and acceptance criteria.

**Template:**

**Step 1 — Meta (reflect)**: Re‑articulate the target and success signal.
**Step 2 — Decompose**: Partition into minimal sub‑tasks.
**Step 3 — Seed**: Start one sub‑task with crisp constraints.

**When I use it**: Whenever I feel fuzzy about the objective.

**Note from my practice**: Meta first prevents me from accelerating in the wrong direction.


---

## Seed → ConstraintsAdd → ScopeTighten

**ID**: sequence_seed_constraintsadd_scopetighten

**Difficulty**: beginner

**Moves**: Seed, ConstraintsAdd, ScopeTighten

**Description**: I define the task, add guardrails, then narrow scope to hit a crisp target.

**Use Cases**: exec summaries, release notes, lesson abstracts

**Example Prompts:**
- Draft a summary of [topic] for a general audience.
- Add constraints: 150 words, 3 bullets max, avoid jargon.
- Limit scope to sections 2–4 only.

**Template:**

**Step 1 — Seed**: State the task plainly.
**Step 2 — ConstraintsAdd**: Add measurable bounds.
**Step 3 — ScopeTighten**: Exclude everything that isn’t the target.

**When I use it**: To get crisp output fast without overreach.

**Note from my practice**: Well‑chosen constraints give me better first passes than endless iterations.


---

## Probe → Compare → Refine

**ID**: sequence_probe_compare_refine

**Difficulty**: intermediate

**Moves**: Probe, Compare, Refine

**Description**: I generate alternatives, compare on criteria, then merge or refine the winner.

**Use Cases**: tool selection, study plan methods, feature approach

**Example Prompts:**
- List 4 solutions with brief pros/cons.
- Compare them on cost, speed, and quality; score 1–5 on each.
- Refine the top option by incorporating the best elements from others.

**Template:**

**Step 1 — Probe**: Produce viable alternatives.
**Step 2 — Compare**: Score on 2–3 chosen criteria.
**Step 3 — Refine**: Improve the top candidate with borrow‑and‑blend.

**When I use it**: Structured decisions where trade‑offs matter.

**Note from my practice**: A light scoring pass stops me from chasing shiny options.


---

## Decompose → Seed → Recurse

**ID**: sequence_decompose_seed_recurse

**Difficulty**: intermediate

**Moves**: Decompose, Seed, Recurse

**Description**: I break down a goal, seed the first unit of work, then iterate upwards.

**Use Cases**: feature delivery, research sprints, course unit planning

**Example Prompts:**
- Break the project into sequential steps with deliverables.
- Seed Step 1: acceptance criteria, risks, and a draft checklist.
- Improve Step 1 using feedback, then propose Step 2’s seed.

**Template:**

**Step 1 — Decompose**: Ordered steps with outputs.
**Step 2 — Seed**: Fully specify the next executable chunk.
**Step 3 — Recurse**: Iterate stepwise and roll improvements upward.

**When I use it**: For long efforts where momentum matters.

**Note from my practice**: Keeps me shipping instead of endlessly planning.


---

## RoleShift → Probe → Compare

**ID**: sequence_roleshift_probe_compare

**Difficulty**: beginner

**Moves**: RoleShift, Probe, Compare

**Description**: I adopt a role to reveal blind spots, explore fixes, then evaluate trade‑offs.

**Use Cases**: UX tweaks, documentation passes, presentation edits

**Example Prompts:**
- As a new user, what confuses me in this flow?
- Suggest 3 improvements that reduce confusion most.
- Compare those against the time required to implement.

**Template:**

**Step 1 — RoleShift**: Choose a perspective (novice, expert, stakeholder).
**Step 2 — Probe**: Generate role‑aware remedies.
**Step 3 — Compare**: Evaluate on impact vs. effort.

**When I use it**: To balance empathy with pragmatism.

**Note from my practice**: Role‑switching makes assumptions visible to me.


---

## Seed → Probe → ScopeLoosen

**ID**: sequence_seed_probe_scopeloosen

**Difficulty**: beginner

**Moves**: Seed, Probe, ScopeLoosen

**Description**: I define the problem, explore options, then deliberately widen context to catch adjacencies.

**Use Cases**: habit design, study plans, backup strategies

**Example Prompts:**
- Plan a weekly exercise routine.
- Offer 5 variations for different energy levels.
- Broaden: include low‑equipment and travel scenarios.

**Template:**

**Step 1 — Seed**: Define the base task.
**Step 2 — Probe**: Provide options.
**Step 3 — ScopeLoosen**: Add adjacent contexts so plans survive real life.

**When I use it**: Planning under uncertainty.

**Note from my practice**: Adding adjacencies reduces my plan‑fragility.


---

## Probe → FormatControl → Refine

**ID**: sequence_probe_formatcontrol_refine

**Difficulty**: beginner

**Moves**: Probe, FormatControl, Refine

**Description**: I explore ideas, structure them into a usable format, then tighten language.

**Use Cases**: content planning, meeting prep, backlog grooming

**Example Prompts:**
- Give me 6 ideas for the article’s angle.
- Organize them in a table with audience, promise, and proof.
- Refine rows 2 and 4 to be punchy and specific.

**Template:**

**Step 1 — Probe**: Generate raw material.
**Step 2 — FormatControl**: Force a structure (table/outline/checklist).
**Step 3 — Refine**: Edit for clarity and specificity.

**When I use it**: Turning brainstorms into assets.

**Note from my practice**: A structure makes weak ideas obvious to me.


---

## FormatControl → Seed → Refine

**ID**: sequence_formatcontrol_seed_refine

**Difficulty**: beginner

**Moves**: FormatControl, Seed, Refine

**Description**: I choose the output skeleton first, then fill it, then iterate.

**Use Cases**: status updates, case summaries, lesson drafts

**Example Prompts:**
- Use this outline: {Problem, Approach, Outcome, Next Steps}.
- Populate it using my notes: [paste notes].
- Refine the transitions and remove jargon.

**Template:**

**Step 1 — FormatControl**: Declare the structure up front.
**Step 2 — Seed**: Fill it with relevant content.
**Step 3 — Refine**: Improve flow and readability.

**When I use it**: For repeatable documents and updates.

**Note from my practice**: Front‑loading structure keeps me from wandering.


---

## Hypothesis → Probe → Meta

**ID**: sequence_hypothesis_probe_meta

**Difficulty**: advanced

**Moves**: Hypothesis, Probe, Meta

**Description**: I start with a testable guess, explore needed evidence, then reflect on confidence and next steps.

**Use Cases**: analytics planning, study diagnostics, market hunches

**Example Prompts:**
- Hypothesis: churn spikes during onboarding, not after.
- What evidence would confirm or falsify this? List data and quick checks.
- Reflect: what’s my confidence now, and what’s the next smallest test?

**Template:**

**Step 1 — Hypothesis**: State a falsifiable claim.
**Step 2 — Probe**: Identify signals, counter‑signals, and checks.
**Step 3 — Meta**: Update confidence and plan the next measurement.

**When I use it**: Anytime I catch myself assuming without evidence.

**Note from my practice**: This stops me from bias‑confirming in loops.


---

## ConstraintsAdd → ScopeTighten → Refine

**ID**: sequence_constraintsadd_scopetighten_refine

**Difficulty**: intermediate

**Moves**: ConstraintsAdd, ScopeTighten, Refine

**Description**: I add guardrails, narrow to the core slice, then polish for delivery.

**Use Cases**: accessibility audits, policy edits, QA sweeps

**Example Prompts:**
- Constraints: must be ADA compliant and mobile‑friendly.
- Narrow to color/contrast only for this pass.
- Refine the palette and annotations for handoff.

**Template:**

**Step 1 — ConstraintsAdd**: Introduce hard requirements.
**Step 2 — ScopeTighten**: Select one slice to tackle now.
**Step 3 — Refine**: Prepare a crisp deliverable.

**When I use it**: Iterative compliance or quality passes.

**Note from my practice**: A narrow lane lets me finish instead of dabbling.


---

## Seed → Meta → Seed

**ID**: sequence_seed_meta_seed

**Difficulty**: beginner

**Moves**: Seed, Meta, Seed

**Description**: I seed a task, reflect if it’s the right target, then re‑seed with the corrected aim.

**Use Cases**: stakeholder comms, cover letters, lesson hooks

**Example Prompts:**
- Draft a 3‑slide pitch for [idea].
- Meta: who is the real decision‑maker and what do they care about?
- Re‑seed the pitch aimed at that person’s priorities.

**Template:**

**Step 1 — Seed**: Produce a first swing.
**Step 2 — Meta**: Check audience/goal alignment.
**Step 3 — Seed**: Re‑issue the task with the aligned target.

**When I use it**: When early drafts feel weirdly off.

**Note from my practice**: Mid‑course correction beats polishing the wrong thing.


---

## Probe → Recurse → Refine

**ID**: sequence_probe_recurse_refine

**Difficulty**: beginner

**Moves**: Probe, Recurse, Refine

**Description**: I generate, build on the strongest candidate, then tighten the result.

**Use Cases**: titles/captions, taglines, UI microcopy

**Example Prompts:**
- List 8 potential headlines.
- Expand only headline #3 into a short intro paragraph.
- Refine the paragraph to be vivid and concrete.

**Template:**

**Step 1 — Probe**: Create a spread of candidates.
**Step 2 — Recurse**: Deepen one candidate with context.
**Step 3 — Refine**: Edit for impact and clarity.

**When I use it**: Creative choices where quality emerges in layers.

**Note from my practice**: Layering avoids overcommitting to a weak seed.


---

## Meta → ScopeTighten → Compare

**ID**: sequence_meta_scopetighten_compare

**Difficulty**: intermediate

**Moves**: Meta, ScopeTighten, Compare

**Description**: I reflect, narrow the target, then compare two precise options.

**Use Cases**: product flows, study schedules, process tweaks

**Example Prompts:**
- Meta: what’s the primary metric I’m trying to move?
- Narrow: optimize only for onboarding time, not conversion.
- Compare two flows side‑by‑side against that metric.

**Template:**

**Step 1 — Meta**: Re‑identify the single success metric.
**Step 2 — ScopeTighten**: Optimize only for that metric.
**Step 3 — Compare**: Evaluate two candidate solutions strictly on metric impact.

**When I use it**: Decision knots where criteria keep multiplying.

**Note from my practice**: Strict criteria discipline keeps me from hedging.


---

## RoleShift → ScopeTighten → ScopeLoosen

**ID**: sequence_roleshift_scopetighten_scopeloosen

**Difficulty**: advanced

**Moves**: RoleShift, ScopeTighten, ScopeLoosen

**Description**: I use a new role to find specifics, then widen to implications before I decide.

**Use Cases**: policy/UX balance, safety reviews, rubric design

**Example Prompts:**
- As a compliance officer, what details matter most here?
- Narrow: list only the non‑negotiable requirements.
- Widen: what follow‑on effects will those requirements have on usability?

**Template:**

**Step 1 — RoleShift**: Choose a role that spotlights different risks.
**Step 2 — ScopeTighten**: Extract the must‑haves.
**Step 3 — ScopeLoosen**: Anticipate cross‑effects before committing.

**When I use it**: Balancing strict requirements with human impact.

**Note from my practice**: This prevents me from shipping rigid but unusable outputs.


---
