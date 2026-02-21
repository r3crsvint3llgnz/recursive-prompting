# Move Analysis

Move frequency is not the same as move importance. The most common move in this corpus — Probe at ~13.8% of 1,980 operations — is not the highest-leverage one. The rarest move — Hypothesis at ~0.8% — correlates with the sharpest quality inflections in the sessions where it appears. Understanding this corpus requires separating how often each move appears from what each move actually does to session trajectory.

---

## Frequency Distribution

Approximate counts. These reflect the observed corpus of 1,980 operations; treat percentages as rounded to the nearest half-point.

| Move            | Approx. Count | Approx. % | Primary Function                                   |
| --------------- | ------------- | --------- | -------------------------------------------------- |
| Probe           | ~274          | ~13.8%    | Expand solution space; surface assumptions         |
| Scope Tighten   | ~267          | ~13.5%    | Constrain focus; re-anchor to constraints          |
| Format Control  | ~238          | ~12.0%    | Specify output structure, length, format           |
| Seed            | ~218          | ~11.0%    | Establish task context and initial constraints     |
| Refine          | ~198          | ~10.0%    | Iterative tightening of most-recent output         |
| Scope Loosen    | ~158          | ~8.0%     | Expand a constraint that has become too tight      |
| Add Constraints | ~158          | ~8.0%     | Introduce new limiting conditions mid-session      |
| Role Shift      | ~139          | ~7.0%     | Change model's operating persona or standpoint     |
| Recurse         | ~139          | ~7.0%     | Apply session logic to a sub-component             |
| Decompose       | ~99           | ~5.0%     | Break complex task into explicit sub-components    |
| Compare         | ~79           | ~4.0%     | Force side-by-side evaluation of options           |
| Meta            | ~69           | ~3.5%     | Audit session trajectory; detect and correct drift |
| Hypothesis      | ~16           | ~0.8%     | Generate competing explanatory framings            |

Total: ~1,980 operations across 441 threads (mean: ~4.5 moves/session).

---

## What the Distribution Reveals

The framework is front-loaded toward exploration and scope management. Probe + Scope Tighten together account for ~27% of all operations — more than a quarter of every session, on average, spent either opening the solution space or tightening around it. This reflects the core dynamic the framework addresses: model outputs default toward the high-probability center of the distribution, and practitioners must actively expand away from that center before they can productively converge on it.

Format Control at ~12% is higher than expected and reflects a practical reality: models make implicit formatting choices that affect how output is read and used. A practitioner who doesn't specify format explicitly gets the model's default, which is frequently verbose and structurally undifferentiated. Format Control is not a high-concept move — it is table stakes for workable output.

The high-level moves — Meta at 3.5%, Hypothesis at 0.8% — are low-frequency by design. Meta is a regulatory interrupt, not a workhorse. Hypothesis is a diagnostic tool for sessions where the model has converged on a framing that may be wrong. Both moves cost attention budget and consume context space. Using them at every step would be counterproductive. Their value is in their rarity: when a session needs them and doesn't get them, the degradation is measurable.

---

## Transition Patterns

Moves don't operate in isolation. The corpus reveals several stable sequential dyads and a clear recovery pattern.

**Probe → Scope Tighten** is the most stable dyad in the corpus, appearing in ~34% of all sessions. The logic is mechanical: Probe expands the solution space (often generating more options than the practitioner needs), and Scope Tighten then constrains focus to the productive subset. This dyad is the backbone of the exploratory divergence pattern — it's how sessions navigate from "what is possible" to "what is relevant."

**Seed → Probe** is the standard session opening for expert practitioners (~28% of sessions). The seed establishes constraints; the probe immediately tests whether those constraints are sufficient or whether the solution space has uninspected corners. Sessions that open with Seed → Refine (jumping directly to tightening without exploration) score 19% lower on signal density on average.

**Meta → Decompose** is the standard recovery sequence for drifted sessions. Meta identifies that the session has gone off-track; Decompose re-structures the task from the current position rather than trying to patch the drift. This dyad appears in approximately 8% of all sessions — which maps closely to the estimated drift rate for sessions exceeding 6 moves.

**Decompose → Recurse** appears in ~14% of sessions, concentrated in the highest-scoring quartile. After breaking a task into components, Recurse applies the full session loop to each component individually. This is the sequence pattern that most distinguishes structured sessions from sessions that merely use multiple moves — it produces compounded gains rather than additive ones.

---

## What Move Frequency Says About Skill Level

Novices over-index on Seed and Refine. The typical novice session opens with a long, heavily specified seed and then runs Refine 3–5 times in sequence, tightening the original output without ever expanding the solution space. This pattern produces locally coherent outputs that score adequately on Relevance and Completeness but rarely achieve top-quartile Signal Density because the practitioner is polishing the model's first-response default rather than steering toward an optimal one.

Experts are distinguished by their willingness to use Meta and Hypothesis. Meta requires acknowledging that the session might be wrong and actively checking. Hypothesis requires generating multiple competing framings rather than committing to the first plausible one. Both moves require intellectual comfort with uncertainty mid-session — the willingness to destabilize something that looks fine in order to find out whether it is actually fine.

The most reliable single predictor of session quality in this corpus is not move count — it is whether Meta appeared at least once. Sessions with at least one Meta operation score, on average, 38% higher composite than sessions without it, regardless of total move count.

---

_Recursive Prompting™ by Seth Robins — Recursive Intelligence™ | [CC BY-SA 4.0](LICENSE.md)_
