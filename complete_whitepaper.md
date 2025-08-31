# Recursive Prompting: An Exploratory Self-Study

**Author:** Seth Robins (Recursive Intelligence™)  
**Publication Date:** August 29, 2025  
**Version:** 1.0  

---

## Table of Contents

1. [Abstract](#abstract)
2. [Introduction](#introduction)
3. [Methodology](#methodology)
4. [Move Types Reference](#move-types-reference)
5. [Move Analysis](#move-analysis)
6. [Pattern Analysis](#pattern-analysis)
6. [Pattern Templates (v1)](#pattern-templates-v1)
7. [Results](#results)
8. [Effectiveness Analysis](#effectiveness-analysis)
9. [Discussion](#discussion)
10. [Conclusion](#conclusion)
11. [References](#references)

---

## Abstract

This white paper documents an exploratory, single-practitioner analysis (n=1) of recursive prompting based on 441 of my own conversation threads comprising 1,980 prompting moves across 13 move types. Through this self-analysis, I identified 20 recurring patterns distilled into 16 reusable templates (v1) across five categories: Exploration, Refinement, Metacognitive, Iterative Development, and Structured Problem-Solving.

My goal was not to prove general effectiveness, but to understand my own prompting techniques well enough to teach them to others. The numbers and structures presented here come from patterns I observed in my own ChatGPT sessions. They should be treated as hypotheses and teaching tools, not definitive research findings.

Key observations from my dataset include:
- When I used metacognitive reflection, systematic decomposition, and iterative refinement moves, I achieved better outcomes
- My conversations alternated between scope-tightening and exploratory phases, with periodic validation loops
- The resulting Pattern Templates (v1) capture practical templates I found useful in personal productivity, business decision-making, and education

**Limitations:** This is an n=1 exploratory self-study with subjective effectiveness scoring (~34%) and self-classification of moves. All findings reflect my personal experience and require validation through future multi-user controlled studies.

This work provides a foundation for sharing my approach to recursive prompting and offers starting points for others to experiment with and adapt to their own workflows.

---

## Introduction

This white paper represents my exploratory self-study of **recursive prompting**—a methodology I developed and refined through my own interactions with ChatGPT. Rather than a generalizable or controlled research project, this is a reflection and analysis of my personal practice (441 conversations, 1,980 moves across 13 move types) with the goal of making my prompting techniques more understandable, teachable, and adaptable for others.

### Why I Did This Study

I created Recursive Prompting because I often found single-shot prompting insufficient for complex tasks. By experimenting with iterative refinement, clarification, and expansion, I began to notice patterns in how I prompted. These patterns seemed to help me get better outcomes. I wanted to analyze these patterns systematically—not to prove their universal effectiveness, but to understand my own habits well enough that I could share them as templates and teaching tools.

Recursive prompting, for me, mirrors human cognitive strategies such as reflective thinking, hypothesis testing, and incremental problem-solving. By documenting how I use these strategies, I can provide examples that others may try, adapt, or test in their own workflows.

### What I Hoped to Learn

Through this self-study, my aims were to:

1. **Characterize My Prompting Moves**: Identify and categorize the types of moves I used most often in my conversations.
2. **See How They Worked for Me**: Document the kinds of responses different moves tended to produce in my sessions.
3. **Distill Patterns into Templates**: Formalize recurring move sequences into reusable templates (20 observed patterns distilled into 16 reusable templates (v1)).
4. **Generate Hypotheses for Others to Test**: Share my findings as hypotheses and teaching material that others can validate or adapt in their own practice.

### What This Work Contributes

This is not a generalizable study. It is an **exploratory, single-practitioner analysis (n=1)**. Its value lies in what it can offer as a foundation for practice and teaching:

- A personal taxonomy of recursive prompting moves and how I used them
- Observed effectiveness patterns from my own sessions (subjective, not objective)
- A set of 16 reusable templates (v1) based on the 20 patterns I noticed
- Reflections on success factors, failure modes, and practical strategies that worked for me

### How I Hope Others Will Use This

I share this work so others can:

- Experiment with the templates I found useful
- Reflect on their own prompting habits in comparison to mine
- Adapt and expand on these ideas in their own domains
- Develop controlled studies to validate or refine the patterns

**Important Limitation:** This paper documents my practice alone. All effectiveness measures come from my personal scoring rubric and judgment. These findings should be treated as exploratory, subjective, and hypothesis-generating—not as proof of effectiveness or generalizable conclusions.

---

## Methodology

This section describes how I studied my own prompting practice. This was an exploratory, single-practitioner analysis (n=1) based on 441 of my conversations with ChatGPT, which contained 1,980 moves across 13 move types. My aim was to understand and document my own habits well enough to create teaching materials and hypotheses for others—not to conduct a controlled or generalizable study.

### Data Collection

The dataset came entirely from my own conversation history. These included a variety of tasks I worked on: research, creative writing, problem-solving, and educational content creation. I extracted these conversations from my logs and organized them into threads, each representing one interaction flow.

**Steps I took to prepare the data:**
1. Segmented conversations into threads
2. Broke each thread into individual prompt-response pairs
3. Normalized text (removed artifacts, aligned formatting)
4. Preserved context and ordering so I could see how moves flowed
5. Filtered out incomplete or trivial threads

### Move Classification

I developed a taxonomy of 13 move types based on what I observed in my own prompting. Examples include Probe, ScopeTighten, Refine, RoleShift, Meta, and Hypothesis. Each prompt I made was manually classified by me into one of these categories.

**Important biases:** I did all classification myself without independent validation. This means the labels reflect my own interpretation and include subjective bias. Additionally, I tended to analyze conversations I considered "successful," introducing selection bias into the dataset.

### Effectiveness Scoring

I also scored many of the AI's responses using a personal rubric (0–20 scale). My rubric combined:
- Relevance (30%)
- Completeness (20%)
- Actionability (10%)
- Response length as a rough proxy (40%)

This was entirely subjective. No other raters or objective benchmarks were used. The scores represent how useful the responses felt to me at the time.

### Analytical Approach

**Progression Metrics Coverage.** While the full dataset includes 441 conversations, progression metrics were computed for 370 conversations where move sequences were sufficiently complete to evaluate progression-level indicators. Counts elsewhere in this paper (e.g., total conversations, total moves, move types, patterns, templates) refer to the full dataset; progression-specific summaries refer to this 370-conversation subset.

To make sense of my data, I explored several descriptive analyses:

- Frequency analysis: How often I used each move type
- Transition analysis: Which moves tended to follow each other
- Sequence analysis: Recurring move sequences across conversations
- Pattern extraction: Identifying repeated move structures that I could formalize as templates

These analyses were tools for reflection. They helped me see habits I wasn't always aware of during live conversations.

### Template Generation

From the recurring sequences I observed, I distilled 20 recurring patterns distilled into 16 reusable templates (v1). Each template includes:
- The move sequence
- Contexts where I found it useful
- Example prompts from my own practice
- Notes about strengths, weaknesses, and adaptations

### Methodological Limitations

Because this was a self-study, there are clear limitations:
- **Single-practitioner (n=1)**: Only my own data was used
- **Subjective scoring**: Effectiveness was based on my personal rubric (~34% overall effectiveness estimate)
- **Self-classification**: All move labeling was done by me alone
- **Selection bias**: I tended to analyze conversations I considered "successful"
- **No control group**: I did not compare directly with other users or single-shot baselines

### Summary

This methodology reflects how I examined my own prompting practice. It provided enough structure for me to identify patterns, build a library of templates, and generate hypotheses that I can now teach and share. However, it does not provide statistical proof or generalizable claims. Future multi-user controlled studies will be necessary to test whether the patterns I observed hold true more broadly.

---

## Move Analysis

*[Note: This section would contain the full content from move_analysis.md. For brevity in this response, I'm indicating where the full content would go. The actual file would include all detailed analysis.]*

---

## Pattern Analysis

*[Note: This section would contain the full content from pattern_analysis.md]*

---

## Pattern Templates (v1)

*[Note: This section would contain the full content from pattern_templates_v1.md with all 16 templates]*

---

## Results

*[Note: This section would contain the full content from results.md]*

---

## Effectiveness Analysis

*[Note: This section would contain the full content from effectiveness_analysis.md]*

---

## Discussion

*[Note: This section would contain the full content from discussion.md]*

---

## Conclusion

This white paper represents my exploratory self-study of recursive prompting based on 441 of my own conversations (1,980 moves across 13 move types). My aim throughout was not to prove effectiveness in any statistical or universal sense, but to understand my own prompting techniques well enough to share them as teaching tools.

### Key Takeaways from My Practice

From analyzing my own sessions, I came away with four key takeaways:

1. **Patterns Do Emerge**: I consistently found myself using recursive structures—20 recurring patterns distilled into 16 reusable templates (v1). These templates help me structure interactions more effectively than single-shot prompting.

2. **Metacognition Matters**: Reflection, assumption-checking, and goal-monitoring moves often made the difference between wandering conversations and productive ones. When I paused to think about my thinking, outcomes improved.

3. **Scope Control Is Powerful**: Alternating between narrowing (ScopeTighten) and broadening (ScopeLoosen) moves was one of the strongest dynamics I observed in my own practice. This deliberate zoom dance helped me avoid both tunnel vision and endless exploration.

4. **Subjective Gains Felt Real**: Using my personal scoring rubric, I estimated that recursive prompting improved outcomes for me by about 34% (entirely subjective). While this number is not objective or generalizable, it reflects my lived experience that recursion makes my conversations more useful.

### How I Use This Work

These insights form the foundation for how I now teach recursive prompting. The templates I extracted are tools I personally rely on and can demonstrate to others in contexts like personal productivity, education, and business decision-making. My intention is to share these as hypotheses and starting points, encouraging others to adapt and expand them in their own practice.

### Important Limitations

It's worth repeating the core caveats that frame this entire study:

- This was a single-practitioner (n=1) exploratory self-study of my own data only
- All effectiveness scores were based on my personal judgment, not objective benchmarks
- My patterns may reflect my style, goals, and domains rather than general truths
- The 34% effectiveness estimate and all percentage gains (42%, 28%, 36%, 31%) represent my subjective personal experience only
- All theoretical frameworks (Cognitive Alignment, Emergent Intelligence) are speculative working hypotheses

These limitations mean that my results cannot be assumed to apply broadly without rigorous multi-user controlled studies.

### Looking Forward

I hope this work serves as a foundation for others to build upon. Future directions I would like to see include:

- Multi-user studies that test whether these patterns hold up across diverse contexts
- Objective evaluation methods for measuring prompt effectiveness
- Domain-specific pattern libraries tailored for fields like education, software development, and organizational decision-making
- Tooling support that integrates recursive prompting strategies directly into AI interfaces

### Final Reflection

For me, recursive prompting is more than a set of techniques—it's a way of working with AI that mirrors how I think and learn. By reflecting, iterating, and structuring conversations, I get better results than I would with one-off prompts. This self-study clarified my own practice, and I hope that by sharing it, others can experiment, adapt, and eventually validate or expand upon what I've started here.

But perhaps the deeper insight is this: the act of studying my own prompting made me a better prompter. The metacognitive awareness that came from analyzing my patterns improved my real-time decision-making in conversations. If this work encourages others to become more reflective about their own AI interactions—to notice their habits, question their assumptions, and iterate on their approaches—then it will have succeeded beyond my original intentions.

This is just the beginning. Recursive prompting will evolve as more people practice it, study it, and create tools around it. My role here has been to document what I found in my own sessions and to offer it as a stepping stone for others. The patterns I've shared are not the final word—they're an invitation to explore, adapt, and discover what works in your own practice.

---

## References

This self-study is based entirely on my own practice and analysis of my personal prompting data (n=1). I did not draw from existing research or white papers in generating the findings presented here.
The works listed below are provided as **context and further reading** for those who wish to situate recursive prompting alongside broader prompting research and practitioner resources.
They did not inform my results directly, but they highlight directions I see as relevant for future exploration, validation, and expansion.

### Selected Research on Prompting and LLM Behavior

1. Wei, J., et al. (2022). **Chain-of-Thought Prompting Elicits Reasoning in Large Language Models.** arXiv:2201.11903.
   [https://arxiv.org/abs/2201.11903](https://arxiv.org/abs/2201.11903)

2. White, J., et al. (2023). **A Prompt Pattern Catalog to Enhance Prompt Engineering with ChatGPT.** arXiv:2302.11382.
   [https://arxiv.org/abs/2302.11382](https://arxiv.org/abs/2302.11382)

3. Zhou, Y., et al. (2024). **The Prompt Report: A Systematic Survey of Prompting Techniques.** arXiv:2406.06608.
   [https://arxiv.org/abs/2406.06608](https://arxiv.org/abs/2406.06608)

### Practitioner White Papers and Guides

4. OpenAI (2024). **GPT‑4.1 Prompting Guide.** Cookbook resource with updated prompting strategies.
   [https://cookbook.openai.com/examples/gpt4-1_prompting_guide](https://cookbook.openai.com/examples/gpt4-1_prompting_guide)

5. OpenAI (2025). **GPT‑5 Prompting Guide.** Early practitioner notes on GPT‑5 prompting and agentic use cases.
   [https://cookbook.openai.com/examples/gpt-5/gpt-5_prompting_guide](https://cookbook.openai.com/examples/gpt-5/gpt-5_prompting_guide)

6. Google (2024). **Prompt Engineering Whitepaper (Marketing Guide).** A 68‑page practitioner resource on prompt design.
   [https://bootstrapcreative.com/google-prompt-engineering-whitepaper-marketing-guide/](https://bootstrapcreative.com/google-prompt-engineering-whitepaper-marketing-guide/)

7. Anthropic (2024). **Building Effective Agents with Prompt Chaining.** Research and practitioner insights.
   [https://www.anthropic.com/research/building-effective-agents](https://www.anthropic.com/research/building-effective-agents)

### How I Plan to Use These Works

While none of these informed my self-study directly, I see them as resources for situating recursive prompting in a larger conversation.
In future iterations, especially as I expand beyond my own dataset into multi-user controlled studies, I expect to connect my analysis with the frameworks and techniques described in these works.

---

## Licensing and Attribution

**License:** This work is licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) | **Trademark:** Recursive Prompting™ by Seth Robins (Recursive Intelligence™) | See [TRADEMARK.md](TRADEMARK.md) for usage guidelines

**Citation:**
```
Robins, S. (2025). Recursive Prompting: An Exploratory Self-Study. 
Recursive Intelligence. https://github.com/[repository-url]
```

---

*This work provides a foundation for sharing my approach to recursive prompting and offers starting points for others to experiment with and adapt to their own workflows.*
