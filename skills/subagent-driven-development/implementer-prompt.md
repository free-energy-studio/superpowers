# Implementer Brief

Give the agent:

- The concrete task and its acceptance criteria.
- Relevant context or the canonical spec, not the entire conversation.
- The workspace, owned files, and dependencies already available.
- Existing patterns and required verification.
- Explicit authority for edits, commits, and external actions.

Ask:

> Implement the requested behavior using the simplest coherent change.
> Preserve unrelated work. Do not change branches or commit anyone else's edits.
> Inspect relevant code before relying on the plan's assumptions.
> Test observable behavior and verify the changed path.
> Resolve routine implementation details; raise consequential ambiguity or missing
> authority before crossing that boundary. Do not delegate unless asked.
>
> Review your diff for correctness, scope, and unnecessary complexity.
> Return what changed, the checks actually run and their results, and remaining
> concerns. Include commit IDs only if committing was part of your task.

Use a report file only when a durable handoff needs it. A short response is often
enough. Do not require status enums or duplicate the same evidence in two places.
