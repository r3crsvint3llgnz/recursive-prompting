# Methodology

## The Dataset

The analysis draws from 441 of my own interaction threads with language models, accumulated over active practice. These are not samples of a broader population — they are the primary source records of how I actually steered models on real tasks. The thread count represents a natural boundary: enough to identify structural patterns, not so many that pattern extraction required automated tooling.

The 441 threads produced 1,980 discrete steering operations, which I classified into the 13-move taxonomy described in the reference section. A subset of 370 threads had sufficient depth (defined as four or more sequential steering moves with measurable output progression) to support transition mapping — analysis of which moves reliably produce stable follow-on states.

## Extraction Process

**Thread segmentation.** Conversations were divided into goal-oriented units. Where a single conversation contained multiple distinct tasks, each task was treated as a separate thread. Exploratory tangents and incomplete task attempts were discarded.

**Structural stripping.** Within each thread, I removed the topical content — the specific subject matter of each conversation — to expose the underlying move sequence. This normalization step is what makes comparison across different domains possible. A thread about software architecture and a thread about a business proposal can both show the same structural pattern: Probe → Scope Tighten → Decompose → Refine. The topics are noise; the sequence is the signal.

**Classification.** Each prompt was assigned one primary move from the 13-move taxonomy. Where a prompt executed multiple moves (a common pattern in expert-level steering), the dominant structural intent determined the classification.

**Persistence audit.** Threads were verified to be complete — that is, that the interaction reached a terminal output I considered final. Abandoned threads and partial completions were excluded.

## Scoring Rubric

Output quality was measured against a 20-point rubric applied to the final output of each complete thread, scored relative to an unstructured single-shot baseline for the same task.

| Dimension | Weight | What it measures |
|---|---|---|
| Relevance | 30% | Did the output respect the stated constraints? |
| Completeness | 20% | Were all sub-tasks addressed? |
| Actionability | 10% | Can the output be used without further human modification? |
| Signal Density | 40% | Ratio of substantive content to filler, hedges, and hallucinated padding |

Signal density carries the highest weight because it is the most reliable proxy for whether I actually used the output. High-relevance outputs that pad to length still fail the practical test.

## Bias and Limits

This is self-assessed, single-practitioner research. I classified my own prompts against a taxonomy I developed, and I scored the outputs against criteria I defined. Confirmation bias is a genuine concern — a practitioner who believes the framework works will find evidence that it works.

I have not attempted to eliminate that bias. I have attempted to document it clearly so readers can apply appropriate discount to the results. The mechanical taxonomy is the part of this work most independent of my assessment — the move definitions do not depend on whether my subjective outcome scores are accurate. The performance deltas do.

The appropriate use of the n=1 data: as evidence that the structural patterns are real and that systematic steering produces measurable differences in signal density. Not as a precise measurement of those differences.

---

*Recursive Prompting™ by Seth Robins — Recursive Intelligence™ | [CC BY-SA 4.0](LICENSE.md)*
