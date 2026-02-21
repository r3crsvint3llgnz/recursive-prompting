# Manifesto: The Architecture of Reasoning

Prompt engineering, as the term is commonly used, describes something too small. It describes word choice. The assumption underneath it is that the right phrasing unlocks the right output — that the model is a lock and the user is hunting for the correct key.

This framework starts from a different premise. Language models do not have keys. They have probability distributions conditioned on context. What controls output quality is not the phrasing of a single prompt. It is the structure of the entire interaction — what context exists, what constraints are active, what the model has been asked to verify, and when the human re-anchors against drift.

Recursive Prompting formalizes that structure. It identifies the 13 operations that do real work in a steering loop, names the failure modes each one addresses, and establishes the minimal viable sequence for reliable output: generate options, commit to one, improve the result. Everything beyond that baseline applies to specific failure classes — shallow depth, premature commitment, scope creep, goal displacement — each of which has a diagnosable symptom and a corrective move.

The discipline this requires is not technical. It is architectural. Before sending the first prompt, define what success looks like. Specify what the output must and must not contain. Choose the move that fits the dominant failure mode of the task type. Monitor for drift. Intervene when it appears.

A model running without structural control does not produce bad outputs most of the time. It produces plausible outputs — outputs that satisfy the surface requirements of the request without reliably satisfying the underlying goal. The gap between plausible and useful is where the discipline lives.

The model's output is not a function of the model. It is a function of the structure built around the model's execution. This framework builds that structure.

---

*Recursive Prompting™ by Seth Robins — Recursive Intelligence™*
