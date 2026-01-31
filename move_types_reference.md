**Navigation:** [← Back to Learning Path](learning_path.md) | [Next: Pattern Templates →](pattern_templates_v1.md)

---

# Steering Moves Reference

> [!NOTE]
> **Epistemic Status:** Personal Observation (n=1). Validation pending.
> These definitions come from an analysis of my own practice. They are not universal laws; they are mechanical levers I use to steer the model.

## The 13 Core Steering Moves

This is the taxonomy of **Prompt Control**. These are the atomic actions you can take to guide a model. Do not use them randomly. Use them to solve specific control problems.

---

## 1. Probe

**Definition:** Generate multiple options, alternatives, or perspectives to explore the solution space.

**Problem it Solves:** Premature commitment. The model (and usually you) will lock onto the first plausible idea. **Probe** forces the hidden options to the surface so you can choose the best one, not just the first one.

**Example Prompts:**
- "Give me 5 different approaches to [problem], each with pros and cons."
- "Brainstorm 8 potential headlines for this article."
- "What are 6 ways I could structure this presentation?"

**Practice Drill:**
*Take a simple decision (e.g., "What to eat for dinner"). Force yourself to generate 5 distinct options before you allow yourself to choose one. Feel the resistance to pausing.*

---

## 2. ScopeTighten

**Definition:** Narrow focus to a specific subset, constraint, or slice of the problem.

**Problem it Solves:** Hallucination and drift. When the model tries to do everything, it does nothing well. **ScopeTighten** acts as a lens, forcing all processing power onto a single, simplified target.

**Example Prompts:**
- "Focus *only* on the mobile user experience."
- "Limit scope to sections 2-4 only."
- "Consider only solutions that cost under $1000."

**Practice Drill:**
*Take a broad topic (e.g., "Climate Change"). Narrow it three times recursively until you are looking at a single, actionable atom (e.g., "Climate Change" → "Urban adaption" → "Roof paint policy in Phoenix").*

---

## 3. ScopeLoosen

**Definition:** Widen perspective to include broader context, adjacent concerns, or system-level effects.

**Problem it Solves:** Tunnel vision. Optimization of a part can destroy the whole. **ScopeLoosen** checks for systemic fit.

**Example Prompts:**
- "Zoom out: how does this affect the end-to-end user flow?"
- "Broaden: include low-equipment and travel scenarios."
- "What are the wider organizational implications?"

---

## 4. FormatControl

**Definition:** Specify the structure, format, or organization of the output.

**Problem it Solves:** Unusable data. A wall of text effectively hides information. **FormatControl** forces the model to synthesize, not just generate.

**Example Prompts:**
- "Organize this in a table with columns for cost, time, and risk."
- "Use this outline: Problem, Approach, Outcome, Next Steps."
- "Format as a checklist with clear action items."

---

## 5. Seed

**Definition:** Establish initial context, constraints, and success criteria for a task.

**Problem it Solves:** The "Blank Page" problem. If you don't set the initial state, the model will hallucinate one.

**Example Prompts:**
- "Here's my goal and constraints: [detailed context]."
- "Draft a summary of [topic] for a general audience."

---

## 6. Refine

**Definition:** Improve, polish, or iterate on existing content or solutions.

**Problem it Solves:** First-draft quality. The model's first output is rarely its best. **Refine** applies specific polish to a known quantity.

**Example Prompts:**
- "Refine this to be clearer and more actionable; remove filler."
- "Improve the transitions and remove jargon."

**Practice Drill:**
*Take a generated paragraph. Ask the model to "cut word count by 30% without losing meaning." Watch what disappears.*

---

## 7. ConstraintsAdd

**Definition:** Introduce specific limitations, requirements, or guardrails.

**Problem it Solves:** Generic output. Authenticity comes from friction. Constraints force the model to be creative rather than defaulting to the average.

**Example Prompts:**
- "Add constraints: 150 words, 3 bullets max, avoid jargon."
- "Must be ADA compliant and mobile-friendly."

---

## 8. RoleShift

**Definition:** Adopt a specific perspective, persona, or stakeholder viewpoint.

**Problem it Solves:** Blind spots. You are trapped in your own perspective. **RoleShift** forces the model to simulate a different mind, revealing risks you cannot see.

**Example Prompts:**
- "As a skeptical reviewer, call out risks I'm missing."
- "Evaluate this as a new user who's never seen our product."

**Practice Drill:**
*Ask the model to explain a concept. Then ask it to "explain it again as a hostile witness." Observe how the facts stay the same but the narrative changes.*

---

## 9. Recurse

**Definition:** Build upon, iterate, or develop previous outputs further.

**Problem it Solves:** Shallow depth. Single-shot prompts can't go deep because they run out of context/attention. **Recurse** allows you to build a skyscraper one floor at a time.

**Example Prompts:**
- "Expand only headline #3 into a short intro paragraph."
- "Build on option 2 by adding implementation details."

---

## 10. Meta

**Definition:** Step back to reflect on the process, goals, or approach itself.

**Problem it Solves:** Getting lost. Sometimes the prompt isn't the problem; the goal is. **Meta** checks the map.

**Example Prompts:**
- "Quick check: what's the actual question I'm trying to answer?"
- "Meta: who is the real decision-maker and what do they care about?"

---

## 11. Compare

**Definition:** Evaluate options against specific criteria or each other.

**Problem it Solves:** Decision paralysis. **Compare** forces a rubric onto subjective options.

**Example Prompts:**
- "Compare these on cost, speed, and quality; score 1-5 on each."
- "Evaluate these approaches against our success criteria."

---

## 12. Decompose

**Definition:** Break complex problems into smaller, manageable components.

**Problem it Solves:** Overwhelm. The model cannot hold a novel 10,000-word output in its head. It can hold a 500-word step.

**Example Prompts:**
- "Break this project into sequential steps with deliverables."
- "Split this into 3-5 sub-tasks with clear inputs/outputs."

---

## 13. Hypothesis

**Definition:** Form testable predictions or assumptions that can be validated.

**Problem it Solves:** Assumption creep. We often treat guesses as facts. **Hypothesis** forces us to label them correctly.

**Example Prompts:**
- "Hypothesis: churn spikes during onboarding, not after."
- "What evidence would confirm or falsify this claim?"

---

**Navigation:** [← Back to Learning Path](learning_path.md) | [Next: Pattern Templates →](pattern_templates_v1.md)

---

**License:** This work is licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) | **Trademark:** Recursive Prompting™ by Seth Robins (Recursive Intelligence™)
