# Pattern Analysis: The Architecture of Stability

**Navigation:** [← Back to README](README.md) | [Results](results.md)

---

Individual moves are atoms. Patterns are molecules.

In my analysis of 441 threads, I looked for the stable sequences—the chains of [Steering Moves](move_types_reference.md) that produced repeatable, high-quality results regardless of the topic. 

## Scaffolding Taxonomy

I identified five primary categories of interaction architecture. These are the defensive barriers we build against drift.

### 1. Exploration Scaffolds (Divergent)
Used to widen the solution space. These patterns force the model to present the map before the traveler chooses a path.
*   **Core Flow**: [Seed → Probe → Compare](pattern_templates_v1.md#probe--compare--scopetighten)
*   **Yield**: Prevents premature convergence.

### 2. Refinement Scaffolds (Convergent)
Used to polish the signal. These are iterative loops that remove the generic "average" of an LLM's first output.
*   **Core Flow**: [Initial → Critique → Revise](pattern_templates_v1.md#critique--revise--validate)
*   **Yield**: High signal density and constraint respect.

### 3. Metacognitive Scaffolds (Systemic)
The "pause" patterns. These are used to debug the reasoning process itself.
*   **Core Flow**: [Reflect → Question → Adjust](pattern_templates_v1.md#reflect--question--verify--adjust)
*   **Yield**: Resolves context drift and logic contradictions.

### 4. Development Scaffolds (Incremental)
The build-up patterns. Used for complex architectures like software or multi-stage plans.
*   **Core Flow**: [Build → Test → Expand](pattern_templates_v1.md#build--test--expand--integrate)
*   **Yield**: Structural integrity and modular progress.

### 5. Problem-Solving Scaffolds (Analytical)
The systematic breakdown of fuzzy goals into actionable atoms.
*   **Core Flow**: [Define → Decompose → Solve](pattern_templates_v1.md#define--decompose--solve--synthesize)
*   **Yield**: High actionability in complex domains.

## From Analysis to Templates

The 20 recurring patterns generated the [v1 Template Library](pattern_templates_v1.md). 

Each template is a **Cognitive Firmware** update. Instead of inventing a sequence from scratch, the practitioner can apply a pre-validated structure. This reduces the cognitive load on the human, allowing them to focus on steering rather than mechanics.

---

**Next:** [Pattern Templates v1](pattern_templates_v1.md)
