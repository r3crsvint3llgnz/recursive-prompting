# Introduction

Language models fail in predictable ways. They drift from the stated goal as context extends. They commit to the first plausible option before exploring the search space. They hedge when they should claim, expand when they should focus, and stop correcting themselves when no correction mechanism exists. None of these are random failures. They follow from the architecture: autoregressive probability estimation over an extending context, with no built-in feedback loop for goal re-anchoring.

Recursive Prompting builds that feedback loop externally. The framework defines 13 steering moves — atomic operations each targeting one class of predictable failure — and a default three-move control loop that handles the majority of tasks without additional structure. This document series records how those moves were identified, what they do mechanically, and how to apply them in sequences that produce reliable outcomes.

The study underlying this framework analyzed 441 interaction threads comprising 1,980 discrete steering operations, conducted by a single practitioner over a defined period. The performance figures reported throughout are real but carry n=1 constraints; the methodological section is explicit about those limits. The mechanical taxonomy, however, does not depend on the performance figures to be useful. Practitioners can apply the moves and observe effects directly.

For the full technical account of why standard prompting approaches fail at the architectural level, start with [Section 01: Why Simple Prompting Fails](01-introduction-problem-focused.md).
