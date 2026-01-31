**Navigation:** [← Back to README](README.md) | [Learning Path](learning_path.md)

---

# Methodology: Extracting the Mechanism

> [!NOTE]
> **Epistemic Status:** Practitioner Log. 
> This is a post-hoc analysis of 441 conversation threads. The goal is to expose the underlying architecture of success, not to perform a blind trial.

I do not believe in magic prompts. I believe in mechanical loops. To understand why some interactions succeed while others drift into noise, I stripped my own practice down to its atoms.

## The Dataset: 441 Threads of Control

The data is derived from 441 of my own interaction threads with Large Language Models. These are not "samples"; they are the primary source records of 1,980 discrete **Steering Moves**.

**The Extraction Process:**
1.  **Segmentation**: Conversations were sliced into discrete, goal-oriented threads.
2.  **Structural Stripping**: Text was normalized. All implicit local context—the "noise" of a specific topic—was removed to reveal the mechanical sequence.
3.  **Persistence Audit**: Each thread was verified to ensure the sequence was complete. Trivial or aborted threads were discarded.

## The Taxonomy: Core Steering Moves

I classified 1,980 prompts into 13 **Core Steering Moves**. 

This classification is a **Cognitive Scaffolding** exercise. I am mapping the invisible paths of reasoning I use to steer the model. By labeling a move as a [Probe](move_types_reference.md#1-probe) or a [ScopeTighten](move_types_reference.md#2-scopetighten), I make the reasoning visible.

> [!IMPORTANT]
> **Bias Management:** As a single-practitioner (n=1) study, these labels reflect my own interpretation. Bias is not a flaw; it is the signature of the practitioner. I analyze successful seeds to understand the shape of success.

## The Rubric: Scoring System Performance

I evaluated system output using a 20-point mechanical rubric. Reliability is not a feeling; it is a measurable state.

*   **Relevance (30%)**: Did the output respect the constraints?
*   **Completeness (20%)**: Were all sub-tasks in the [Decompose](move_types_reference.md#12-decompose) move addressed?
*   **Actionability (10%)**: Can the output be used without further human modification?
*   **Signal Density (40%)**: Ratio of usable content to filler/hallucinated padding.

## Analytical Layer

Analysis was performed across 370 threads where sequences were sufficiently deep to reveal progression-level indicators.

*   **Frequency Analysis**: Identifying the most reliable "starting moves."
*   **Transition Mapping**: Understanding which moves create a stable "Follow-on" effect.
*   **Pattern Distillation**: Recognizing the stable molecules of prompting—the sequences that work regardless of the topic.

---

**Summary:** This methodology provides the scaffolding for the v1 taxonomy. It is an engineering audit of a cognitive process.
