# Move Analysis: The Atoms of Steering

**Navigation:** [← Back to README](README.md) | [Methodology](methodology.md)

---

I do not guess; I measure. In my analysis of 441 interaction threads, I mapped 1,980 discrete **Steering Moves**. This is the data on how those moves distribute across a successful control loop.

## Move Frequency Distribution

Reliability correlates with frequency. In my dataset, the workload is overwhelmingly carried by the **Probe** and **Scope Control** moves.

| Steering Move      | Frequency | Percentage | Role in Loop |
|--------------------|-----------|------------|--------------|
| [Probe](move_types_reference.md#1-probe) | 274 | 13.8% | Divergence |
| [ScopeTighten](move_types_reference.md#2-scopetighten) | 267 | 13.5% | Convergence |
| [ScopeLoosen](move_types_reference.md#3-scopeloosen) | 266 | 13.4% | Context Expansion |
| [FormatControl](move_types_reference.md#4-formatcontrol) | 248 | 12.5% | Constraint |
| [Seed](move_types_reference.md#5-seed) | 211 | 10.7% | Initialization |
| [Refine](move_types_reference.md#6-refine) | 122 | 6.2% | Iteration |
| [ConstraintsAdd](move_types_reference.md#7-constraintsadd) | 102 | 5.2% | Precision |
| [RoleShift](move_types_reference.md#8-roleshift) | 152 | 7.7% | Perspective |
| [Recurse](move_types_reference.md#9-recurse) | 148 | 7.5% | Feedback |
| [Meta](move_types_reference.md#10-meta) | 70 | 3.5% | Metacognition |
| [Compare](move_types_reference.md#11-compare) | 67 | 3.4% | Evaluation |
| [Decompose](move_types_reference.md#12-decompose) | 38 | 1.9% | Architecture |
| [Hypothesis](move_types_reference.md#13-hypothesis) | 15 | 0.8% | Epistemic Test |

## High-Leverage Observations

1.  **Metacognition Leverage**: While [Meta](move_types_reference.md#10-meta) represents only 3.5% of the moves, it correlates with a disproportionate increase in output relevance. It is the lever that moves the world.
2.  **The Zoom Ratio**: The balance between [Tighten](move_types_reference.md#2-scopetighten) and [Loosen](move_types_reference.md#3-scopeloosen) (13.5% vs 13.4%) is nearly 1:1. Success is a rhythmic oscillation, not a linear path.
3.  **The Structural Gap**: Low-frequency moves like [Decompose](move_types_reference.md#12-decompose) and [Hypothesis](move_types_reference.md#13-hypothesis) are specialized tools. They are the "deep repairs" used when the context has become too fuzzy for high-frequency moves to fix.

## Transition Thermodynamics: The Flow of Control

Moves do not exist in isolation. They form sequences—the "molecules" of prompting.

*   **[Probe → Refine]**: The most common sequence for creative synthesis.
*   **[Seed → Probe]**: The standard initialization for research tasks.
*   **[Meta → Decompose]**: The recovery sequence. Used to restart a drifting context.

---

**Next Analysis:** [Pattern Analysis & Template Generation](pattern_analysis.md)
