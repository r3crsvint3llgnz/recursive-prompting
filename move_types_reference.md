**Navigation:** [← Previous: Methodology](methodology.md) | [Back to Index](README.md) | [Next: Move Analysis →](move_analysis.md)

---

# Recursive Prompting Move Types Reference

## The 13 Core Move Types

This reference guide provides clear definitions and examples for each of the 13 move types that form the foundation of Recursive Prompting™. These moves can be combined into sequences and patterns to create more sophisticated prompting strategies.

---

## 1. Probe

**Definition:** Generate multiple options, alternatives, or perspectives to explore the solution space.

**Purpose:** Divergent thinking, brainstorming, exploring possibilities

**Example Prompts:**
- "Give me 5 different approaches to [problem], each with pros and cons"
- "Brainstorm 8 potential headlines for this article"
- "What are 6 ways I could structure this presentation?"

**When to Use:** Early in the process when you need breadth before depth, or when stuck and need fresh perspectives.

---

## 2. ScopeTighten

**Definition:** Narrow focus to a specific subset, constraint, or slice of the problem.

**Purpose:** Convergent thinking, reducing complexity, focusing effort

**Example Prompts:**
- "Focus only on the mobile user experience"
- "Limit scope to sections 2-4 only"
- "Consider only solutions that cost under $1000"

**When to Use:** When overwhelmed by complexity, need to make progress on one piece, or want to avoid scope creep.

---

## 3. ScopeLoosen

**Definition:** Widen perspective to include broader context, adjacent concerns, or system-level effects.

**Purpose:** Systems thinking, catching blind spots, considering implications

**Example Prompts:**
- "Zoom out: how does this affect the end-to-end user flow?"
- "Broaden: include low-equipment and travel scenarios"
- "What are the wider organizational implications?"

**When to Use:** After detailed work to check for unintended consequences, or when solutions feel too narrow.

---

## 4. FormatControl

**Definition:** Specify the structure, format, or organization of the output.

**Purpose:** Making information usable, forcing clarity, enabling comparison

**Example Prompts:**
- "Organize this in a table with columns for cost, time, and risk"
- "Use this outline: Problem, Approach, Outcome, Next Steps"
- "Format as a checklist with clear action items"

**When to Use:** When raw information needs structure, preparing deliverables, or making complex data comparable.

---

## 5. Seed

**Definition:** Establish initial context, constraints, and success criteria for a task.

**Purpose:** Setting foundation, providing context, defining scope

**Example Prompts:**
- "Here's my goal and constraints: [detailed context]"
- "Draft a summary of [topic] for a general audience"
- "Plan a weekly exercise routine for someone with limited time"

**When to Use:** At the beginning of new tasks, when context is unclear, or to reset direction.

---

## 6. Refine

**Definition:** Improve, polish, or iterate on existing content or solutions.

**Purpose:** Quality improvement, clarity enhancement, optimization

**Example Prompts:**
- "Refine this to be clearer and more actionable; remove filler"
- "Improve the transitions and remove jargon"
- "Polish this paragraph to be more vivid and concrete"

**When to Use:** After initial drafts, when content exists but needs improvement, or in final editing phases.

---

## 7. ConstraintsAdd

**Definition:** Introduce specific limitations, requirements, or guardrails.

**Purpose:** Focusing creativity, ensuring compliance, managing resources

**Example Prompts:**
- "Add constraints: 150 words, 3 bullets max, avoid jargon"
- "Must be ADA compliant and mobile-friendly"
- "Requirements: under $500 budget, completed in 2 weeks"

**When to Use:** When outputs are too broad, need to meet specific requirements, or want to force creative solutions.

---

## 8. RoleShift

**Definition:** Adopt a specific perspective, persona, or stakeholder viewpoint.

**Purpose:** Revealing blind spots, stress-testing ideas, empathy building

**Example Prompts:**
- "As a skeptical reviewer, call out risks I'm missing"
- "Evaluate this as a new user who's never seen our product"
- "From a compliance officer's perspective, what details matter most?"

**When to Use:** To challenge assumptions, get fresh perspectives, or ensure solutions work for different stakeholders.

---

## 9. Recurse

**Definition:** Build upon, iterate, or develop previous outputs further.

**Purpose:** Deepening solutions, progressive development, layered improvement

**Example Prompts:**
- "Expand only headline #3 into a short intro paragraph"
- "Build on option 2 by adding implementation details"
- "Take the best elements from each approach and combine them"

**When to Use:** When initial outputs show promise but need development, or for iterative improvement.

---

## 10. Meta

**Definition:** Step back to reflect on the process, goals, or approach itself.

**Purpose:** Course correction, clarity checking, process optimization

**Example Prompts:**
- "Quick check: what's the actual question I'm trying to answer?"
- "Meta: who is the real decision-maker and what do they care about?"
- "Reflect: what's my confidence now, and what's the next smallest test?"

**When to Use:** When feeling stuck, direction seems unclear, or before major decisions.

---

## 11. Compare

**Definition:** Evaluate options against specific criteria or each other.

**Purpose:** Decision making, trade-off analysis, objective evaluation

**Example Prompts:**
- "Compare these on cost, speed, and quality; score 1-5 on each"
- "Evaluate these approaches against our success criteria"
- "Compare two flows side-by-side against user onboarding time"

**When to Use:** When choosing between alternatives, need objective evaluation, or making trade-off decisions.

---

## 12. Decompose

**Definition:** Break complex problems into smaller, manageable components.

**Purpose:** Reducing complexity, enabling parallel work, clarifying dependencies

**Example Prompts:**
- "Break this project into sequential steps with deliverables"
- "Split this into 3-5 sub-tasks with clear inputs/outputs"
- "Decompose this workflow into its component parts"

**When to Use:** When problems feel overwhelming, need to delegate work, or want to tackle pieces systematically.

---

## 13. Hypothesis

**Definition:** Form testable predictions or assumptions that can be validated.

**Purpose:** Scientific thinking, assumption testing, evidence-based decisions

**Example Prompts:**
- "Hypothesis: churn spikes during onboarding, not after"
- "What evidence would confirm or falsify this claim?"
- "State a testable prediction about user behavior"

**When to Use:** When making assumptions, need evidence-based decisions, or want to test theories systematically.

---

## Move Frequency in Practice

Based on analysis of 1,980 moves across 441 conversations:

| Move Type      | Frequency | Percentage | Usage Notes |
|----------------|-----------|------------|-------------|
| Probe          | 274       | 13.8%      | Most common - great for exploration |
| ScopeTighten   | 267       | 13.5%      | Essential for focus and progress |
| ScopeLoosen    | 266       | 13.4%      | Balances tightening, prevents tunnel vision |
| FormatControl  | 248       | 12.5%      | Critical for usable outputs |
| Seed           | 211       | 10.7%      | Foundation move for new tasks |
| RoleShift      | 152       | 7.7%       | Powerful for perspective shifts |
| Recurse        | 148       | 7.5%       | Builds depth and quality |
| Refine         | 122       | 6.2%       | Polish and improvement |
| ConstraintsAdd | 102       | 5.2%       | Focuses creativity effectively |
| Meta           | 70        | 3.5%       | Rare but high-impact when used |
| Compare        | 67        | 3.4%       | Essential for decisions |
| Decompose      | 38        | 1.9%       | Less frequent but breakthrough-enabling |
| Hypothesis     | 15        | 0.8%       | Specialized but powerful for analysis |

## Common Move Transitions

Effective move sequences often follow these patterns:
- **Probe → Refine**: Explore broadly, then polish the best option
- **Seed → Probe**: Establish context, then explore alternatives  
- **Meta → Decompose**: Reflect first, then break down complexity
- **ScopeTighten ↔ ScopeLoosen**: Rhythmic zooming in and out

## Tips for Using Move Types

1. **Start with Seed or Meta** when beginning new tasks
2. **Use Probe early** for divergent thinking
3. **Alternate ScopeTighten/ScopeLoosen** to balance focus and perspective
4. **Apply RoleShift** to challenge your assumptions
5. **End with Refine** to polish outputs
6. **Use Meta** when stuck or changing direction
7. **Combine moves** into sequences for complex tasks

---

**Navigation:** [← Previous: Methodology](methodology.md) | [Back to Index](README.md) | [Next: Move Analysis →](move_analysis.md)

---

**License:** This work is licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) | **Trademark:** Recursive Prompting™ by Seth Robins (Recursive Intelligence™) | See [TRADEMARK.md](TRADEMARK.md) for usage guidelines
