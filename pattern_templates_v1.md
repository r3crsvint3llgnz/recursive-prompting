# Recurring Patterns (Templates Only)

These patterns emerged from personal practice (n=1). They are stable, repeatable sequences that solve specific classes of problems — not universal laws, and not yet validated beyond my own sessions.

---

## Difficulty Legend

- **Novice (The Control Loop)**: Linear, high-reliability sequences. Start here.
- **Practitioner (System Steering)**: Sequences that involve comparison, trade-offs, or structural shifts.
- **Expert (Metacognition)**: Non-linear sequences involving reflection, assumption checking, and high-order reasoning.

---

## 1. Novice Patterns (The Essentials)

A novice doesn't yet trust the model enough to deliberately withhold direction early — the instinct is to front-load all constraints in the first prompt rather than letting Probe surface the option space first. These patterns build the habit of separating generation from selection before commitment.

_Goal: Stop guessing, start steering. Use these for 80% of daily tasks._

### Probe → ScopeTighten → Refine

_The "Generic Control Loop". If you only learn one, learn this._

- **Moves**: [Probe](move_types_reference.md#1-probe) → [ScopeTighten](move_types_reference.md#2-scopetighten) → [Refine](move_types_reference.md#6-refine)
- **Use Case**: Email drafting, summarizing, simple creation.
- **Why it works**: Separates divergence (Probe) from convergence (Tighten) and polish (Refine), preventing the blank-page freeze. Without that separation, the model tries to generate and commit simultaneously — producing a best-guess output that was never fully explored and never truly chosen, leaving you to edit from a starting position you didn't consciously select.
- **Example Prompt Sequence**:
  1.  "Brainstorm 6 options; keep them concise."
  2.  "Focus only on option 3. Expand it."
  3.  "Refine the draft: shorter sentences, no jargon."

### FormatControl → Seed → Refine

_The "Form Filler"._

- **Moves**: [FormatControl](move_types_reference.md#4-formatcontrol) → [Seed](move_types_reference.md#5-seed) → [Refine](move_types_reference.md#6-refine)
- **Use Case**: Monthly reports, status updates, repeatable docs.
- **Why it works**: Front-loading the structure lets the model fill content into a skeleton rather than decide layout and generate substance at the same time. Without the skeleton, those two constraints compete — structure emerges emergently rather than intentionally, which means it drifts from your template on every subsequent run.

---

## 2. Practitioner Patterns (Trade-offs & Systems)

A practitioner already runs the basic loop reliably — the gap is handling problems where the right answer isn't obvious at the start, where trade-offs exist, or where different stakeholders apply different criteria. Practitioner patterns require knowing when to stop iterating on a single answer and start comparing alternatives or applying adversarial pressure.

_Goal: Handle complexity and multiple stakeholders._

### Seed → Probe → RoleShift

_The "Blind Spot Checker"._

- **Moves**: [Seed](move_types_reference.md#5-seed) → [Probe](move_types_reference.md#1-probe) → [RoleShift](move_types_reference.md#8-roleshift)
- **Use Case**: Planning, strategy, high-stakes emails.
- **Why it works**: You get the standard plan first, but RoleShift forces the model to attack its own work, revealing weaknesses you missed. Without the shift, the model extends and elaborates rather than critiques — it was trained to be helpful, so it leans toward confirmation, and adversarial pressure only appears if you explicitly demand it.

### Probe → Compare → Refine

_The "Decision Assistant"._

- **Moves**: [Probe](move_types_reference.md#1-probe) → [Compare](move_types_reference.md#11-compare) → [Refine](move_types_reference.md#6-refine)
- **Use Case**: Choosing tools, hiring decisions, prioritization.
- **Why it works**: Compare forces a matrix or rubric evaluation, turning subjective text into objective rankings. Without it, the model hands you a list of options but leaves the comparison work to you — which is exactly the cognitive load you were trying to offload.

### ScopeTighten → ScopeLoosen → Recurse

_The "Zoom Lens"._

- **Moves**: [ScopeTighten](move_types_reference.md#2-scopetighten) → [ScopeLoosen](move_types_reference.md#3-scopeloosen) → [Recurse](move_types_reference.md#9-recurse)
- **Use Case**: Bug fixing, system policy changes.
- **Why it works**: Ensures you fix the specific bug (Tighten) without breaking the whole system (Loosen). Without the Loosen step, the fix looks correct in isolation and fails in context — you've solved the symptom and missed the propagation.

---

## 3. Expert Patterns (Metacognition)

Expert patterns address something Practitioner patterns don't: the possibility that the problem definition itself is wrong. A practitioner can navigate complexity within a given frame; these patterns force you to question the frame before you navigate it — and to do that well, you need enough domain knowledge to recognize a bad frame when you see one.

_Goal: Fix the question before fixing the answer._

### Meta → Decompose → Seed

_The "Project Rescue"._

- **Moves**: [Meta](move_types_reference.md#10-meta) → [Decompose](move_types_reference.md#12-decompose) → [Seed](move_types_reference.md#5-seed)
- **Use Case**: When you feel stuck or the task feels "fuzzy".
- **Why it works**: Stops you from accelerating in the wrong direction — Meta checks the map before you drive. Without it, a thorough Decompose commits you more deeply to an incorrect framing: the more detailed the plan, the harder it becomes to abandon.

### Hypothesis → Probe → Meta

_The "Scientist"._

- **Moves**: [Hypothesis](move_types_reference.md#13-hypothesis) → [Probe](move_types_reference.md#1-probe) → [Meta](move_types_reference.md#10-meta)
- **Use Case**: Market analysis, debugging weird errors.
- **Why it works**: Prevents confirmation bias by forcing the explicit statement of a falsifiable claim before you generate evidence. Without an explicit hypothesis first, Probe returns evidence that confirms whatever direction the prompt implies — the model finds what you're looking for because you already told it what to look for.

---

_Recursive Prompting™ by Seth Robins — Recursive Intelligence™ | Pattern templates released under [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/)_
