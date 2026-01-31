# Manifesto: Stop Hoping, Start Steering

**Status:** Living Document  
**Author:** Seth Robins (Recursive Intelligence)

---

The gap between a "magic" result and a "useless" one isn't the model. It's the control loop.

Most people treat Large Language Models like search engines or vague interns. They hand over an overloaded request—*"Write a presentation about AI adoption"*—and hope the machine guesses the right audience, tone, structure, and depth. When it fails, they blame the "hallucination."

That surprise comes from a category error. LLMs are not databases of answers. They are engines of possibility. If you do not constrain the possibility space, you get noise.

## The Architect's View

I am not interested in "prompt engineering" as a collection of magic words. I am interested in **Prompt Control**.

Recursive Prompting is a system for **Cognitive Scaffolding**. It shifts the workload from "guessing" to "steering." It breaks the cognitive blur of a complex task into discrete, mechanical operations—**Moves**—that you can execute, inspect, and correct.

I developed this system because I had to. As an autistic practitioner, I cannot rely on implicit context. I need reasoning to be visible. I need the mechanism to be exposed. When I forced my own LLM interactions into explicit steps, my error rate dropped, and the texture of the output changed. It became solid.

## The Core Concept: Steering Loops

A single-shot prompt collapses exploration, decision-making, and execution into one opaque step. Recursive Prompting separates them.

### The Basic Control Loop

1.  **Probe**: Generate options without commitment. See the shape of the solution space.
2.  **Scope Tighten**: Make a ruthless decision. Pick one path. Kill the others.
3.  **Refine**: Amplify the signal. Apply constraints to the chosen path.

This is not theory. It is a mechanical process. You do not move to step 3 until step 2 is verified.

## Why This Repository Exists

This is an **n=1** exploratory study of that system.

I analyzed 441 of my own conversation threads. I stripped them down to their components. I identified **13 Core Steering Moves** and **16 Recurring Patterns** that consistently produce quality.

This repository is not a library of "perfect prompts." It is a blueprint of the mechanism.

*   **[Learning Path](learning_path.md)**: How to start using the system today.
*   **[Core Moves](move_types_reference.md)**: The atomic units of steering.
*   **[Pattern Templates](pattern_templates_v1.md)**: Proven sequences for specific problems.

## A Note on Rigor

This is a practitioner’s log, not a randomized control trial. The numbers here reflect my own interactions and my own rubric of success. They are heuristics, intended to be tested in your own workflow.

Treat this method like a new tool in your belt. Feel the weight of it. Learn how it handles. Then build something that stands up.
