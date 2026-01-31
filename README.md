# Recursive Prompting: The Architect’s Guide to Prompt Control

**Navigation:** [Manifesto](Manifesto.md) | [Learning Path](learning_path.md) | [Steering Moves](move_types_reference.md) | [Pattern Templates](pattern_templates_v1.md)

---

## Stop Hoping, Start Steering.

Most AI interaction is a gamble. You send a message, cross your fingers, and hope the machine guesses what you need. When the output drifts or "hallucinates," we call it an error. 

I call it a category mistake.

LLMs are not search engines; they are engines of probability. If you don't constrain the possibility space, you get noise. **Recursive Prompting** is a system of **Cognitive Scaffolding** designed to shift the workload from "guessing" to "steering."

This repository contains the blueprints for that mechanism.

> [!IMPORTANT]
> **Core Identity:** This is an **n=1** exploratory study. It represents 1,980 individual steering moves across 441 conversation threads. It is a practitioner's log, not a sanitized academic theory.

---

## The System at a Glance

The core of this method is the **Control Loop**: a mechanical process for isolating decision-making from execution.

1.  **Probe**: Force the model to generate options. See the shape of the solution space.
2.  **Scope Tighten**: Make a ruthless decision. Pick one path and kill the others.
3.  **Refine**: Polish the signal. Apply constraints to the chosen path.

### Key Knowledge Bases

*   **[Manifesto](Manifesto.md)**: The "Why." Read this if you want to understand the philosophy of steering over hoping.
*   **[Learning Path](learning_path.md)**: The "How." Three distinct tracks for Novices, Practitioners, and Analysts.
*   **[Steering Moves Reference](move_types_reference.md)**: The "Atoms." Definitions and data for the 13 core actions of prompt control.
*   **[Pattern Templates](pattern_templates_v1.md)**: The "Molecules." 16 repeatable sequences for solving specific classes of problems.

---

## The Research Data

For those who value precision and evidence:

*   **[Abstract](abstract.md)**: The executive summary of the self-study.
*   **[Methodology](methodology.md)**: How I stripped 441 threads down to their mechanical components.
*   **[Move Analysis](move_analysis.md)**: Statistics on which moves actually move the needle.
*   **[Effectiveness Analysis](effectiveness_analysis.md)**: Where the system stands up—and where it breaks.

---

## License & Usage

This project is licensed under **[CC BY-SA 4.0](LICENSE.md)**.
**Recursive Prompting™** and **Recursive Intelligence™** are trademarks of Seth Robins. See [TRADEMARK.md](TRADEMARK.md) for usage guidelines.

---

*This system was developed by an autistic practitioner who requires reasoning to be visible. It is built for competence, precision, and the optimization of broken systems.*
