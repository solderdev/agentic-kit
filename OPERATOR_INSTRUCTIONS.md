# Operator Instructions (Only for the human operator)

> **Info**
> This list summarizes best-practice methods for communicating with the agent.

Start out by editing the `DESIGN.md` yourself, describe scope, goals, non-goals, constraints, and key decisions or tradeoffs. Later you can let the agent rephrase it.

The clearer your own mental model about the project, the clearer you can convey it to the agent resulting in higher quality output.

Name the subject you are referring to (project, component, file, behavior); avoid vague words like "it" or "that".

Start with intent and context: the change you want and why it matters to the system.

Use clear boundaries and invariants: what must remain true, what must not change, and what can be flexible.

Call out interfaces, entry points, and ownership: who/what is responsible for each part.

Keep communication concise but complete: enough detail to act without guessing.

Prefer concrete examples and edge cases over abstract descriptions.

State assumptions and unknowns explicitly to surface risks early.

Ask for clarification only if ambiguity would materially change the design or implementation.