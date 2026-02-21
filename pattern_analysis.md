# Pattern Analysis

Moves are atoms. Patterns are molecules. The same move — a Probe, a Meta, a Decompose — can appear in multiple distinct patterns with entirely different effects depending on what precedes and follows it. Understanding the framework at the move level tells you what each operation does. Understanding it at the pattern level tells you how to sequence operations for a specific kind of task.

---

## How Patterns Were Identified

441 threads. After each thread, the move sequence was stripped of its content — what remained was a pure structural record: `[Seed → Probe → Scope Tighten → Refine → Refine → Meta → Decompose → Recurse]`. These structural sequences were then analyzed for recurring dyads and triads.

The threshold for counting something as a pattern rather than a coincidence was appearance in at least 15 threads with a positive outcome score (composite score ≥ 14/20). 20 candidate architectures met this threshold. 16 survived a secondary check: stability across domain (the pattern had to produce positive outcomes in at least two of the five task domains, not just in one). The remaining 4 were domain-specific sequences useful in one context but not generalizable enough to be treated as framework-level patterns.

The 16 validated patterns cluster into five functional domains. The domain membership of a pattern is determined by what problem the pattern solves, not by the specific moves it contains.

---

## The Five Functional Domains

### Exploratory Divergence

Exploratory divergence patterns solve the problem of premature convergence. They force the model to generate a broad solution space before committing to any particular path. The canonical form is `Seed → Probe → Probe → Hypothesis → Scope Tighten` — two probes to open competing lines of inquiry, Hypothesis to force explicit framing of the alternatives, Scope Tighten to select among them. These patterns are most valuable at session start, before any output has been accepted as valid, and on tasks where the correct answer is not obvious in advance. They cost exploration overhead but prevent the worst form of quality failure: polishing the wrong answer.

### Iterative Refinement

Refinement patterns solve the problem of output that is on-target but underspecified. They are the most common patterns in the corpus because Refine is a frequent move and the dyad `Scope Tighten → Refine` is the stable backbone of most productive sessions. Refinement patterns are not sophisticated — their value is in execution discipline. A practitioner who Refines without first tightening scope is polishing a moving target. A practitioner who tightens scope before each Refine operation gives the model a fixed surface to improve against, and the output density compounds across iterations. In threads with 3+ Scope Tighten → Refine cycles, signal density was 27% higher than in threads with unconstrained Refine runs of the same length.

### Metacognitive Regulation

Metacognitive regulation patterns solve the problem of undetected drift. They are the least common domain in the corpus — Meta appears in only ~3.5% of operations — but their absence is more costly than any other single omission. The standard metacognitive pattern is `[mid-session] Meta → Decompose → Refine`: audit the session, restructure what remains, tighten the components. This pattern appears in approximately 8% of all threads and is concentrated among the highest-scoring sessions. What distinguishes it from simply inserting a Meta move is the Decompose that follows: when Meta reveals that the session has drifted, the right response is structural reorganization, not incremental patching. Decompose resets the task architecture from the current position, enabling Refine to operate on a clean surface.

### Incremental Development

Incremental development patterns solve the problem of complex multi-part deliverables — documents with multiple sections, code with multiple modules, analyses with multiple dependent claims. The canonical form is `Decompose → Seed(sub) → Refine → Recurse`, repeated for each sub-component. The pattern treats each component as a mini-session nested inside the parent session. This produces better outputs than attempting to generate the whole deliverable in one shot for a mechanically clear reason: each sub-session can be scoped and steered independently, preventing a weak answer in one component from contaminating the framing of adjacent components. In sessions using incremental development patterns on multi-section deliverables, Completeness scores averaged +33% vs. single-pass generation.

### Analytical Decomposition

Analytical decomposition patterns solve the problem of complex analytical tasks where the correct structure is not given and must be derived. The canonical form is `Probe → Decompose → Compare → Hypothesis → Scope Tighten`. Probe surfaces the analytical dimensions worth examining. Decompose structures them into discrete sub-questions. Compare forces side-by-side evaluation of competing answers to each sub-question. Hypothesis generates competing explanatory framings at the integrative level. Scope Tighten commits to the framing best supported by the analysis. This pattern produces the highest-scoring outputs in the corpus on average (+41% composite) and the most structurally complex sessions. It is also the pattern most vulnerable to Metacognitive Neglect — the sequence is long enough that drift can occur between Probe and Hypothesis without a Meta audit to catch it.

---

## Why Domain Matters More Than Individual Patterns

A practitioner who memorizes 16 pattern templates has 16 tools. A practitioner who understands what each domain solves can improvise. The domain tells you what problem you are in; the moves tell you what operations are available; the pattern is whatever sequence solves the problem with the moves at hand.

In practice, the domain frame is what enables mid-session adaptation. If you are in an exploratory divergence task and the Probe → Hypothesis step produces one clearly dominant framing rather than genuine alternatives, you don't need a template to tell you what to do — you know you're in the wrong domain for the current state of the session. Shift to refinement. Tighten scope. The domain diagnosis is the skill; the pattern is the scaffolding around it.

This is the difference between using the framework as a lookup table and using it as a reasoning tool. Lookup table usage produces good results in standard cases. Reasoning tool usage produces good results in non-standard cases too.

---

## The v1 Template Library

The 16 validated patterns are documented in [pattern_templates_v1.md](pattern_templates_v1.md). Each template includes: the pattern's domain, its move sequence, the trigger conditions that indicate it is the right choice, the common failure points, and two worked examples from the corpus.

The template library is for practitioners who are new to the framework and need scaffolding for their scaffolding — a starting point before they have enough session experience to improvise reliably. It is explicitly not a prescription. A practitioner who uses the templates without developing the underlying domain-judgment will perform well on tasks that match the templates and poorly on tasks that don't.

The templates cannot handle sessions that require mid-course domain shifts — tasks that begin as exploratory and transition to analytical, or that begin as incremental development and require metacognitive regulation when a structural flaw is detected mid-build. Those are judgment calls. The templates flag where those calls are most common, but they cannot make them. That is the practitioner's job.

---

_Recursive Prompting™ by Seth Robins — Recursive Intelligence™ | [CC BY-SA 4.0](LICENSE.md)_
