# Steering Moves Reference

These definitions come from an analysis of my own practice. They are not universal laws. They are mechanical levers for steering the model. Epistemic status: personal observation (n=1), validation pending.

## The 13 Core Steering Moves

This is the taxonomy of **Prompt Control**. These are the atomic actions you can take to guide a model. Do not use them randomly. Use them to solve specific control problems.

---

## 1. Probe

**Definition:** Generate multiple options, alternatives, or perspectives to explore the solution space.

**Problem it Solves:** You and the model will both lock onto the first plausible idea and stop. The first plausible idea is rarely the best one — it is just the most available. Probe forces the alternatives to the surface before any single path gets committed.

**Example Prompts:**

- "Give me 5 different approaches to [problem], each with pros and cons."
- "Brainstorm 8 potential headlines for this article."
- "What are 6 ways I could structure this presentation?"

**Practice Drill:**
_Take a simple decision (e.g., "What to eat for dinner"). Force yourself to generate 5 distinct options before you allow yourself to choose one. Feel the resistance to pausing._

---

## 2. ScopeTighten

**Definition:** Narrow focus to a specific subset, constraint, or slice of the problem.

**Problem it Solves:** Without a scope constraint, the model attends to the entire problem space simultaneously and produces output that is superficially relevant to everything and not specifically useful for anything. ScopeTighten forces the attention window onto one target.

**Example Prompts:**

- "Focus _only_ on the mobile user experience."
- "Limit scope to sections 2-4 only."
- "Consider only solutions that cost under $1000."

**Practice Drill:**
_Take a broad topic (e.g., "Climate Change"). Narrow it three times recursively until you are looking at a single, actionable atom (e.g., "Climate Change" → "Urban adaptation" → "Roof paint policy in Phoenix")._

---

## 3. ScopeLoosen

**Definition:** Widen perspective to include broader context, adjacent concerns, or system-level effects.

**Problem it Solves:** When you optimize for one component without considering the full system, you break something you didn't intend to touch. ScopeLoosen pulls the model back to the system level so local improvements don't destroy global coherence.

**Example Prompts:**

- "Zoom out: how does this affect the end-to-end user flow?"
- "Broaden: include low-equipment and travel scenarios."
- "What are the wider organizational implications?"

---

## 4. FormatControl

**Definition:** Specify the structure, format, or organization of the output.

**Problem it Solves:** Raw generation produces output in the model's preferred structure, not yours. Unstructured output forces you to do the cognitive work of parsing and organizing after the fact. FormatControl builds that structure into the output directly, so the result is usable without postprocessing.

**Example Prompts:**

- "Organize this in a table with columns for cost, time, and risk."
- "Use this outline: Problem, Approach, Outcome, Next Steps."
- "Format as a checklist with clear action items."

---

## 5. Seed

**Definition:** Establish initial context, constraints, and success criteria for a task.

**Problem it Solves:** Without explicit context, the model invents it. It makes assumptions about your audience, constraints, and goals that are plausible but wrong. Seed sets the actual starting conditions so the model is optimizing toward your real target, not a hallucinated one.

**Example Prompts:**

- "Here's my goal and constraints: [detailed context]."
- "Draft a summary of [topic] for a general audience."

---

## 6. Refine

**Definition:** Improve, polish, or iterate on existing content or solutions.

**Problem it Solves:** The model's first output is the average of plausible paths through the problem, not the best one. Refine iterates on a specific output with targeted criteria, improving precision rather than regenerating from scratch and losing what already works.

**Example Prompts:**

- "Refine this to be clearer and more actionable; remove filler."
- "Improve the transitions and remove jargon."

**Practice Drill:**
_Take a generated paragraph. Ask the model to "cut word count by 30% without losing meaning." Watch what disappears._

---

## 7. ConstraintsAdd

**Definition:** Introduce specific limitations, requirements, or guardrails.

**Problem it Solves:** Without limits, the model converges toward the most common patterns in its training data — output that is technically correct but generic. Constraints eliminate the default escape routes and force specific, creative solutions rather than statistically average ones.

**Example Prompts:**

- "Add constraints: 150 words, 3 bullets max, avoid jargon."
- "Must be ADA compliant and mobile-friendly."

---

## 8. RoleShift

**Definition:** Adopt a specific perspective, persona, or stakeholder viewpoint.

**Problem it Solves:** You are optimizing from a single stakeholder's perspective. The risks you miss are by definition outside your default view. RoleShift instructs the model to simulate a different viewpoint — a skeptic, a user, a critic — surfacing objections you won't generate yourself.

**Example Prompts:**

- "As a skeptical reviewer, call out risks I'm missing."
- "Evaluate this as a new user who's never seen our product."

**Practice Drill:**
_Ask the model to explain a concept. Then ask it to "explain it again as a hostile witness." Observe how the facts stay the same but the narrative changes._

---

## 9. Recurse

**Definition:** Build upon, iterate, or develop previous outputs further.

**Problem it Solves:** A single prompt tries to hold the full problem space and all its constraints simultaneously. The model can't go deep because it's attending to everything at once. Recurse treats each previous output as a stable foundation and extends from there, one layer at a time.

**Example Prompts:**

- "Expand only headline #3 into a short intro paragraph."
- "Build on option 2 by adding implementation details."

---

## 10. Meta

**Definition:** Step back to reflect on the process, goals, or approach itself.

**Problem it Solves:** Long sessions accumulate context drift — the stated goal and the actual work diverge without anyone noticing. Meta steps out of the content level and checks whether the current direction still leads to the original objective. Sometimes the prompt isn't the problem; the goal is.

**Example Prompts:**

- "Quick check: what's the actual question I'm trying to answer?"
- "Meta: who is the real decision-maker and what do they care about?"

---

## 11. Compare

**Definition:** Evaluate options against specific criteria or each other.

**Problem it Solves:** Without explicit criteria, options get evaluated by gut feel and the first-presented option wins. Compare forces you to name the evaluation criteria before scoring, which separates the analysis from the preference and makes decisions traceable.

**Example Prompts:**

- "Compare these on cost, speed, and quality; score 1-5 on each."
- "Evaluate these approaches against our success criteria."

---

## 12. Decompose

**Definition:** Break complex problems into smaller, manageable components.

**Problem it Solves:** Complex tasks contain hidden dependencies and ambiguities that only become visible when you try to execute. Decompose surfaces those dependencies before you start, not after you're blocked. The model can hold a 500-word step. It cannot hold a coherent 10,000-word output.

**Example Prompts:**

- "Break this project into sequential steps with deliverables."
- "Split this into 3-5 sub-tasks with clear inputs/outputs."

---

## 13. Hypothesis

**Definition:** Form testable predictions or assumptions that can be validated.

**Problem it Solves:** Strategies quietly embed assumptions that were never validated. When those assumptions fail, the strategy fails — and you often can't trace the failure back to its source. Hypothesis surfaces embedded assumptions as explicit claims that can be tested or falsified before you commit to acting on them.

**Example Prompts:**

- "Hypothesis: churn spikes during onboarding, not after."
- "What evidence would confirm or falsify this claim?"

---

_Recursive Prompting™ by Seth Robins — Recursive Intelligence™ | [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)_
