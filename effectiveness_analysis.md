# Effectiveness Analysis

Every framework has failure modes. A framework used without understanding its failure modes is just a more elaborate way to make the same mistakes. These are this one's.

---

## Primary Failure: Metacognitive Neglect

Meta is the lowest-frequency move in the corpus at 3.5% of operations. It is also the highest-leverage one. The first failure mode of the framework is using it without using Meta — executing a full session without ever pausing to audit whether the session is still on track.

The mechanism is straightforward. Language models don't signal when they've drifted. They produce fluent, confident, topically adjacent output whether they're answering your actual question or a nearby question they found easier to answer. Without a manual check — an explicit mid-session move to inspect what the model has in context and compare it against the original objective — drift accumulates silently. By move 6 of a 10-move session, you can be running a skilled iterative refinement loop on the wrong thing.

Metacognitive Neglect is particularly common in sessions that start well. A strong seed plus a good first response creates the impression that the session is on track. The practitioner starts Refining rather than auditing. Signal density holds or even rises locally — the model is producing focused, non-redundant content on the sub-question it latched onto — while objective fulfillment degrades because the sub-question was not the question.

The diagnostic signature: signal density staying high while actionability and objective fulfillment scores drop. When you see that pattern in retrospect, a missed Meta move is almost always the cause.

Fix: Insert a Meta move after every 4–5 moves in any session exceeding 7 moves total. The Meta move does not need to be elaborate — "Before we continue, what is the current objective, and are the last two outputs moving toward it?" is sufficient to reset the model's attention to the session's original frame.

---

## Secondary Failure: Context Drift

Language models use attention mechanisms that weight recent tokens more heavily than distant ones. In practice this means that constraints established in the seed of a long session lose influence over time. The model does not forget them — they remain in context — but they compete for attention weight with everything the session has generated since. By move 10 of a 15-move session, the original scope constraints are often functionally invisible.

Context Drift is distinct from Metacognitive Neglect. Neglect is a practitioner failure — not pausing to audit. Drift is a model failure — constraints gradually losing weight without any obvious signal that they have. A practitioner who audits regularly can still fall victim to drift if they don't actively re-anchor constraints after each audit.

The mechanism makes it predictable: drift accelerates in proportion to session length and output verbosity. A session that generates 3,000 tokens of output before move 7 will experience measurably more drift than a session that generates 800 tokens. Long, verbose responses are not just a quality problem — they are a structural problem that degrades every subsequent move.

Fix: Use Scope Tighten or Add Constraints moves to actively re-anchor the session's constraints every 4–5 moves. Don't just check whether constraints are still in effect — explicitly restate them. Force the model to position its next generation in explicit relationship to the re-stated constraints. This is not redundant. It is maintenance.

---

## Tertiary Failure: Premature Convergence

Premature Convergence is locking onto the first plausible option before the solution space has been adequately explored. It is subtler than Neglect or Drift because its signature looks like success: the model produces a coherent, well-structured response, the practitioner finds it satisfying, and the session closes.

The problem is that the model's first plausible option is its highest-probability default — the answer that fits the input most closely among options the model has learned to generate frequently. For common task types, this default is often excellent. For complex, non-standard tasks, it is often the most familiar-looking answer rather than the best answer.

Premature Convergence costs most in sessions where the task requires genuine originality or where the optimal approach is structurally different from the obvious approach. A strategic analysis that converges on the standard industry framing rather than examining the actual constraints of the specific situation. A technical design that defaults to the most common architectural pattern rather than the one best suited to the system's actual constraints.

Fix: Use Probe + Hypothesis before Refine in any session where originality matters or where the standard answer is known and insufficient. Force the model to generate multiple competing framings before committing to one. The Decompose move reinforces this: breaking the problem into explicit sub-components before generating forces the model to encounter the non-obvious sub-components, not just the prominent ones.

---

## Expert vs. Novice Patterns

Novices front-load. They write long, detailed seeds that attempt to specify every constraint and consideration upfront, then Refine the output until it meets their standard. This strategy is not without value — a careful seed is better than a careless one — but it is fragile. A long seed imposes high constraint before the model has generated anything worth constraining. It also concentrates the practitioner's effort at the start, leaving less capacity for the mid-session steering that most determines final quality.

Experts invert this. They write thin seeds — focused, high-signal starting points that establish the task type, the output format, and the one or two constraints that will shape everything downstream. Then they build density recursively: Probe to expand the solution space, Decompose to structure it, Refine to tighten the sub-components one at a time, Meta to audit trajectory, Scope Tighten to re-anchor when attention drifts.

The expert pattern generates more moves per session (average 6.8 vs. 4.1 for novices in this corpus) and substantially higher signal density at close (+31% vs. novice sessions). The thin seed is not laziness — it is precision about where to put effort.

One specific expert behavior distinguishes high-scoring sessions from all others: willingness to discard and restart. When Meta reveals the session has drifted badly, the expert practitioner starts a new session with updated constraints rather than trying to salvage an off-track one. Novices almost never discard. Experts discard in approximately 12% of sessions.

---

## A Warning

Naming failure modes does not protect you from them. The three failures described here are among the most common patterns in the 441-thread corpus — including later sessions, after the framework was well-established. Metacognitive Neglect and Context Drift appear even in high-scoring sessions, partially compensated by other moves.

The diagnostic index in section 04 provides the inspection criteria and move-level responses for each failure mode. Cross-reference it early. The framework does not self-apply. Each session requires active monitoring, and the failure modes return whenever that monitoring lapses.

---

*Recursive Prompting™ by Seth Robins — Recursive Intelligence™ | [CC BY-SA 4.0](LICENSE.md)*
