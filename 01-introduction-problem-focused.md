# Theoretical Foundations of Iterative LLM Steering: Why Simple Prompting Fails

Large language models are stochastic systems masquerading as deterministic ones. This distinction becomes critical at scale. In any practical application—mission-critical writing, strategic reasoning, code generation, technical documentation—a single prompt-to-completion pipeline introduces systematic vulnerabilities that compound across long contexts. The problem is not prompt quality. It is the model's fundamental architecture.

## The Technical Roots of Instability

LLMs predict tokens autoregressively: `P(wₙ | w₁, …, wₙ₋₁)` via Softmax. This means every token is treated as a probability guess, not a fact. Over a long context window, stochastic noise accumulates. Error rates observed in the wild: 27% for citations, 15% for numerical data. By the time a model completes a complex reasoning task, it has drifted from the original intent—not due to poor prompting, but due to how the architecture decays under load. This is "epistemic drift": a gradual shift from factual grounding to probabilistic hallucination. The longer the interaction, the worse the outcomes.

## Why Existing Frameworks Fall Short

**Chain-of-Thought (CoT)** attempts to remedy this by externalizing intermediate reasoning steps. It works: CoT beats zero-shot prompting on math and logic tasks. But CoT remains linear. A single error in step two cascades through steps three, four, and five. On complex puzzles—the "Game of 24," for instance—CoT fails on the first step 60% of the time. When the foundation cracks, the entire chain collapses.

**Tree-of-Thoughts (ToT)** improves by adding branching and backtracking. Nodes can be evaluated and paths abandoned if they look unpromising. ToT outperforms CoT by ~25% on the same tasks. But this is still single-pass reasoning at each node. The model still generates within a local context window and can still drift. It has multiple chances to fail, not structural protection against failure modes.

**Least-to-Most (LtM)** prompting decomposes hierarchically: break the problem into subproblems, solve them sequentially, and inject each solution into the next prompt as context. This does improve coherence over longer chains—LtM can handle 12+ token sequences where CoT breaks down. But the improvements are cumulative, not fundamental. Each subproblem still faces the same autoregressive decay. Better ordering does not eliminate the underlying stochastic noise.

## The Missing Piece: Iteration

All three frameworks—CoT, ToT, LtM—treat generation as fundamentally one-directional: input → reasoning → output. The assumption is that a well-structured prompt will produce a well-structured output. But that assumption breaks down when context is long, reasoning is complex, or stakes are high.

What is needed is not a better prompt. It is a control loop. Iterative steering introduces cyclical verification and re-anchoring. Instead of hoping a single model pass will succeed, the interaction becomes: generate, inspect, constrain, regenerate. Each cycle resets the stochastic timer, re-anchors the model to verified state, and narrows the solution space. The model stops drifting because it is forcibly re-grounded at regular intervals.

This is why frameworks like Recursive Prompting exist: not as ornamentation, but as a reliability protocol. Iteration is not optional when the stakes matter.
