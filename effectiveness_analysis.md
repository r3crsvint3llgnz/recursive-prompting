# Effectiveness & Failure Modes

**Navigation:** [← Back to README](README.md) | [Results](results.md)

---

Effective control is not a binary state. Even with a formal taxonomy of [Steering Moves](move_types_reference.md), system output can still drift. Success depends on the practitioner’s ability to recognize failure modes and apply the correct mechanical remedy.

## Primary Failure Modes

In my analysis of 441 threads, I identified recurring patterns of system breakdown. These are not model errors; they are control errors.

### 1. Premature Convergence
*   **The Problem**: Settling on a solution before the solution space has been adequately surveyed.
*   **The Symptom**: Generic, predictable, or "safe" outputs that miss the core complexity.
*   **The Remedy**: Force a [Probe](move_types_reference.md#1-probe) move. Generate 5+ alternatives before allowing the system to commit.

### 2. Metacognitive Neglect
*   **The Problem**: Operating on autopilot. Driving faster without checking the map.
*   **The Symptom**: A long thread that is "perfectly" answering the wrong question.
*   **The Remedy**: Apply a [Meta](move_types_reference.md#10-meta) move. Step back to re-verify the success criteria.

### 3. Context Drift (Cognitive Overload)
*   **The Problem**: The thread grows too long, and the model begins to lose the high-level constraints.
*   **The Symptom**: "Hallucinations" or contradictory logic in deep threads.
*   **The Remedy**: Use [Decompose](move_types_reference.md#12-decompose) to reset the state or [Seed](move_types_reference.md#5-seed) a clean context with only the essential variables.

---

## Optimization Strategies

Success is a rhythmic variance between **Divergence** and **Convergence**.

### The Zoom Lens Strategy
Successful practitioners use the **[Tighten → Loosen → Recurse](pattern_templates_v1.md#scopetighten--scopeloosen--recurse)** pattern. They fix the local detail (Tighten), then immediately check for system-wide ripples (Loosen) before proceeding.

### Constraint Friction
Authenticity comes from friction. Generic prompts produce generic text. By using [ConstraintsAdd](move_types_reference.md#7-constraintsadd), you force the model to work for the answer, leading to higher-quality logic.

---

## The Novice Track vs. The Expert Track

*   **Novice**: Focus on the **Control Loop** ([Probe → Tighten → Refine](pattern_templates_v1.md#probe--scopetighten--refine)). Reach for reliability first.
*   **Expert**: Focus on **Metacognitive Scaffolding**. Use the [Meta](move_types_reference.md#10-meta) and [Hypothesis](move_types_reference.md#13-hypothesis) moves to debug the problem itself.

---

**Next:** [Discussion & Implications](discussion.md)
