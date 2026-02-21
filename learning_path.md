# Learning Path

---

## Mastering Recursive Prompting

Learning to steer an LLM is like learning an instrument. You start with the scales, then the chords, then the composition. This path is designed to take you from a "hoper" to an "architect."

### Track 1: The Novice (Reliability Focus)

If you are tired of inconsistent outputs and want a reliable way to get results.

1.  **Read**: The [Manifesto](Manifesto.md) to understand the philosophy of "Steering."
2.  **Learn the Loop**:
    - **[Probe](move_types_reference.md#1-probe)**: "Give me 5 options." (Don't decide yet).
    - **[ScopeTighten](move_types_reference.md#2-scopetighten)**: "Pick option 3. Ignore the rest." (Commit).
    - **[Refine](move_types_reference.md#6-refine)**: "Polish it." (Execute).
3.  **Apply**: Use the **[Probe → ScopeTighten → Refine](pattern_templates_v1.md#probe--scopetighten--refine)** template on your next email or summary task.

**You've completed this track when**: You run a full Probe → ScopeTighten → Refine sequence on a real task without reverting to a single-prompt "just tell me the answer" request. The three-move structure feels natural rather than effortful, and you can look at your prompt history and identify which move each prompt was executing.

**Common mistake that stalls you here**: Writing Probe prompts that are actually fully-specified requests in disguise. "Give me 5 options for a subject line for this email, which should be professional, short, and focused on the Q3 results" has already made the decision. Probe only surfaces the option space if you withhold your constraints and let the model show you what exists before you narrow it.

---

### Track 2: The Practitioner (Complexity Focus)

Once you have the Control Loop down, you need to handle complexity — non-linear problems, system effects, and blind spots.

1.  **Master the Taxonomy**: Read [Steering Moves Reference](move_types_reference.md). Pay attention to **RoleShift** and **Meta**.
2.  **Expand Your Toolkit**: Study the [Pattern Templates](pattern_templates_v1.md).
    - _Decision Paralysis?_ Use **[Meta → ScopeTighten → Compare](pattern_templates_v1.md#meta--scopetighten--compare)**.
    - _Blind Spots?_ Use **[Seed → Probe → RoleShift](pattern_templates_v1.md#seed--probe--roleshift)**.
3.  **Experiment**: Try a **[Tighten → Loosen → Recurse](pattern_templates_v1.md#scopetighten--scopeloosen--recurse)** cycle on a larger project.

**You've completed this track when**: You can look at a failing or drifting output and correctly diagnose which move you need next — not "iterate more," but specifically whether the situation calls for a RoleShift, a Compare, or a Meta check. That diagnosis is the practitioner skill; running the move is just execution.

**Common mistake that stalls you here**: Using Compare when you actually need Meta. If the problem definition is incorrect, Compare produces a ranked list of wrong answers and makes you more confident in the wrong direction. The mistake is treating Practitioner patterns as a progression — you can't apply them more skillfully until you can recognize when the pattern itself is the wrong choice for the current problem.

---

### Track 3: The Analyst (Research Focus)

If you are looking for the data, the n=1 context, or want to contribute to the taxonomy.

1.  **Context**: Read [Abstract](abstract.md) and [Methodology](methodology.md).
2.  **Deep Dive**: Review [Move Analysis](move_analysis.md) for frequency and effectiveness stats.
3.  **Critique**: Read [Effectiveness Analysis](effectiveness_analysis.md) to understand where this system fails.

**You've completed this track when**: You can read the effectiveness analysis and identify a gap that isn't documented there — a failure mode, a domain where the patterns break down, or an assumption in the methodology that the data doesn't actually test. Contributing a critique is the signal, not finishing the reading.

**Common mistake that stalls you here**: Treating the data as confirmation rather than as a starting point for critique. The n=1 context means every pattern in this system needs stress-testing across different domains, users, and task types before it earns the status of "validated." Reading with agreement is not analysis.

---

Learning the moves is not the goal. Using the control loop systematically until it becomes habitual is. The moves are vocabulary; the control loop is grammar; fluency is when you stop thinking about which move comes next and start thinking only about what the output requires. If you find yourself defaulting to single-prompt hoping even after learning the sequences, that is not a knowledge gap — it is a habit gap. The [implementation diagnostics](04-implementation-diagnostics.md) is the recovery resource for exactly that: it identifies the specific failure modes that stall practitioners and gives you a direct intervention for each one.

---

_Recursive Prompting™ by Seth Robins — Recursive Intelligence™ | [CC BY-SA 4.0](LICENSE.md)_
