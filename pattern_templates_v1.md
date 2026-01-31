**Navigation:** [← Back to Learning Path](learning_path.md) | [Core Moves](move_types_reference.md)

---

# Recurring Patterns (Templates Only)

> [!NOTE]
> **Epistemic Status:** Personal Observation (n=1). Validation pending.
> These patterns emerged from my own practice. I found them to be stable, repeatable sequences that solve specific classes of problems.

---

## Difficulty Legend

*   **Novice (The Control Loop)**: Linear, high-reliability sequences. Start here.
*   **Practitioner (System Steering)**: Sequences that involve comparison, trade-offs, or structural shifts.
*   **Expert (Metacognition)**: Non-linear sequences involving reflection, assumption checking, and high-order reasoning.

---

## 1. Novice Patterns (The Essentials)

> *Goal: Stop guessing, start steering. Use these for 80% of daily tasks.*

### Probe → ScopeTighten → Refine
*The "Generic Control Loop". If you only learn one, learn this.*

*   **Moves**: [Probe](move_types_reference.md#1-probe) → [ScopeTighten](move_types_reference.md#2-scopetighten) → [Refine](move_types_reference.md#6-refine)
*   **Use Case**: Email drafting, summarizing, simple creation.
*   **Why it works**: Separates "divergence" (Probe) from "convergence" (Tighten) and "polish" (Refine). Prevents the "blank page" freeze.
*   **Example Prompt Sequence**:
    1.  "Brainstorm 6 options; keep them concise."
    2.  "Focus only on option 3. Expand it."
    3.  "Refine the draft: shorter sentences, no jargon."

### FormatControl → Seed → Refine
*The "Form Filler".*

*   **Moves**: [FormatControl](move_types_reference.md#4-formatcontrol) → [Seed](move_types_reference.md#5-seed) → [Refine](move_types_reference.md#6-refine)
*   **Use Case**: Monthly reports, status updates, repeatable docs.
*   **Why it works**: Front-loading the structure (the skeleton) allows the model to just pour content in, reducing structural hallucinations.

---

## 2. Practitioner Patterns (Trade-offs & Systems)

> *Goal: Handle complexity and multiple stakeholders.*

### Seed → Probe → RoleShift
*The "Blind Spot Checker".*

*   **Moves**: [Seed](move_types_reference.md#5-seed) → [Probe](move_types_reference.md#1-probe) → [RoleShift](move_types_reference.md#8-roleshift)
*   **Use Case**: Planning, strategy, high-stakes emails.
*   **Why it works**: You get the standard plan first, but `RoleShift` forces the model to attack its own work, revealing weaknesses you missed.

### Probe → Compare → Refine
*The "Decision Assistant".*

*   **Moves**: [Probe](move_types_reference.md#1-probe) → [Compare](move_types_reference.md#11-compare) → [Refine](move_types_reference.md#6-refine)
*   **Use Case**: Choosing tools, hiring decisions, prioritization.
*   **Why it works**: `Compare` forces a matrix/rubric evaluation, turning subjective text into objective rankings.

### ScopeTighten → ScopeLoosen → Recurse
*The "Zoom Lens".*

*   **Moves**: [ScopeTighten](move_types_reference.md#2-scopetighten) → [ScopeLoosen](move_types_reference.md#3-scopeloosen) → [Recurse](move_types_reference.md#9-recurse)
*   **Use Case**: Bug fixing, system policy changes.
*   **Why it works**: Ensures you fix the specific bug (Tighten) without breaking the whole system (Loosen).

---

## 3. Expert Patterns (Metacognition)

> *Goal: Fix the question before fixing the answer.*

### Meta → Decompose → Seed
*The "Project Rescue".*

*   **Moves**: [Meta](move_types_reference.md#10-meta) → [Decompose](move_types_reference.md#12-decompose) → [Seed](move_types_reference.md#5-seed)
*   **Use Case**: When you feel stuck or the task feels "fuzzy".
*   **Why it works**: Stops you from accelerating in the wrong direction. `Meta` checks the map before you drive.

### Hypothesis → Probe → Meta
*The "Scientist".*

*   **Moves**: [Hypothesis](move_types_reference.md#13-hypothesis) → [Probe](move_types_reference.md#1-probe) → [Meta](move_types_reference.md#10-meta)
*   **Use Case**: Market analysis, debugging weird errors.
*   **Why it works**: Prevents confirmation bias by forcing the explicit statement of a falsifiable claim.

---

**License:** Pattern templates released under [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/) (Public Domain) | **Trademark:** Recursive Prompting™ by Seth Robins (Recursive Intelligence™)
