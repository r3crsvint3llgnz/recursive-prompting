# References

## Note on Citation Scope

The n=1 methodology and the 13-move taxonomy in this series are derived from the practitioner's own thread analysis. The citations below fall into two categories: (1) works that directly informed specific sections, cited inline in those sections; and (2) works situating Recursive Prompting in the broader prompting research landscape, provided for context and further reading.

Section 01 draws on Wei et al. (2022), Yao et al. (2023), and Zhou et al. (2022) for the technical framing of CoT, ToT, and LtM limitations. Section 03 cites Madaan et al. (2023) for SELF-REFINE performance data. All other sections derive from the practitioner's own analysis.

---

## Works Cited

**Madaan, A., Tandon, N., Gupta, P., Hallinan, S., Gao, L., Wiegreffe, S., Alon, U., Dziri, N., Prabhumoye, S., Yang, Y., Welleck, S., Majumder, B. P., Gupta, S., Yazdanbakhsh, A., & Clark, P.** (2023). SELF-REFINE: Iterative refinement with self-feedback. *Advances in Neural Information Processing Systems (NeurIPS)*, 36. [https://arxiv.org/abs/2303.17651](https://arxiv.org/abs/2303.17651)

> Establishes the three-role self-improvement loop (Generator, Critic, Refiner) requiring no additional training data. Performance data cited in Section 03: mathematical reasoning 22.1% → 59.0%, complex constraint satisfaction 4.4% → 61.3%.

---

**Wei, J., Wang, X., Schuurmans, D., Bosma, M., Ichter, B., Xia, F., Chi, E., Le, Q., & Zhou, D.** (2022). Chain-of-thought prompting elicits reasoning in large language models. *Advances in Neural Information Processing Systems (NeurIPS)*, 35. [https://arxiv.org/abs/2201.11903](https://arxiv.org/abs/2201.11903)

> Foundation paper for Chain-of-Thought prompting. Establishes that externalizing intermediate reasoning steps improves performance on multi-step tasks. Cited in Section 01 for the CoT baseline comparison and its limitation: errors in early reasoning steps cascade through the chain.

---

**Yao, S., Yu, D., Zhao, J., Shafran, I., Griffiths, T., Cao, Y., & Narasimhan, K.** (2023). Tree of thoughts: Deliberate problem solving with large language models. *Advances in Neural Information Processing Systems (NeurIPS)*, 36. [https://arxiv.org/abs/2305.10601](https://arxiv.org/abs/2305.10601)

> Introduces ToT as a branching, backtracking extension of CoT. Cited in Section 01: ToT outperforms CoT by ~25% on complex planning tasks but remains single-pass at each node, preserving the core vulnerability to local context drift.

---

**Zhou, D., Schärli, N., Hou, L., Wei, J., Scales, N., Wang, X., Schuurmans, D., Cui, C., Bousquet, O., Le, Q., & Chi, E.** (2022). Least-to-most prompting enables complex reasoning in large language models. *arXiv preprint arXiv:2205.10625*. [https://arxiv.org/abs/2205.10625](https://arxiv.org/abs/2205.10625)

> Introduces hierarchical decomposition as a prompting strategy: break the problem into subproblems, solve sequentially, inject each solution as context for the next. Cited in Section 01 for LtM's ability to handle chains CoT cannot, and its residual limitation: better ordering does not eliminate autoregressive noise within each subproblem.

---

## Further Reading

The works below were not cited in the main series but provide relevant context for situating Recursive Prompting in the broader field.

**White, J., Fu, Q., Hays, S., Sandborn, M., Olea, C., Gilbert, H., Elnashar, A., Spencer-Smith, J., & Schmidt, D. C.** (2023). A prompt pattern catalog to enhance prompt engineering with ChatGPT. *arXiv preprint arXiv:2302.11382*. [https://arxiv.org/abs/2302.11382](https://arxiv.org/abs/2302.11382)

> A practitioner-facing catalog of prompt patterns. Relevant for comparing pattern-based approaches to the sequence-based approach in this framework.

**Schulhoff, S., Ilie, M., Balepur, N., Kahadze, K., Liu, A., Si, C., Li, Y., Gupta, A., Han, H., Schulhoff, S. I., Dulepet, P. S., Baskaran, S., Kim, M., Kim, B., Stewart, L., Singh, A., Pham, C. H., Bhatt, S., Janciauskis, T., … Gupta, O.** (2024). The prompt report: A systematic survey of prompting techniques. *arXiv preprint arXiv:2406.06608*. [https://arxiv.org/abs/2406.06608](https://arxiv.org/abs/2406.06608)

> Comprehensive survey of prompting techniques across the literature as of mid-2024. Useful for placing this framework's vocabulary and approach within the broader taxonomy of the field.

**Anthropic.** (2024). Building effective agents. *Anthropic Research*. [https://www.anthropic.com/research/building-effective-agents](https://www.anthropic.com/research/building-effective-agents)

> Practitioner and research resource on agentic prompt chaining. Relevant for understanding how multi-step steering loops connect to autonomous agent architectures.

**OpenAI.** (2024). GPT-4.1 prompting guide. *OpenAI Cookbook*. [https://cookbook.openai.com/examples/gpt4-1_prompting_guide](https://cookbook.openai.com/examples/gpt4-1_prompting_guide)

> Model-specific prompting guidance focused on instruction following and agentic behavior. Useful for practitioners implementing this framework on GPT-class models.

---

*Recursive Prompting™ by Seth Robins — Recursive Intelligence™ | [CC BY-SA 4.0](LICENSE.md)*
