---
name: brainstorming
description: Use when a requested feature or behavior change has unresolved requirements or consequential design choices that need discussion before implementation.
---

# Design Together

Use `applying-development-principles`. Understand the user's goal and inspect the
existing path before proposing a new one.

For a clear, bounded implementation request, proceed with the requested change and
appropriate verification. Do not ask the user to approve the same intent again.
For an explanation or investigation, stay in that scope.

When design decisions remain:

1. Establish the desired behavior, constraints, and what counts as working.
   Ask only questions whose answers could materially change the result.
2. Lead with the simplest viable design using existing concepts. Show alternatives
   only when there is a real tradeoff, not to fill a quota.
3. Make important contracts, trust boundaries, and failure behavior concrete.
   Include only the detail needed to judge the proposal.
4. Resolve consequential ambiguity before implementing. A discussion-only request
   ends with the design; it is not authorization to start coding.

Match the artifact to the work. A short explanation in chat may be enough.
For a substantial design or handoff, keep one canonical spec in the user's chosen
location or the repository's convention. Update it instead of duplicating it in
multiple documents. Do not require separate approval for every section and then
the same document again.

Adjust the amount of process as facts emerge, in either direction. New risk may
need a user decision; resolved uncertainty may make a planned framework unnecessary.

Before presenting the design, remove speculative features, redundant fields,
unneeded layers, and choices already settled by existing contracts. Preserve
necessary permissions, privacy boundaries, and correctness guarantees.

Use a diagram or mockup when it clarifies the decision. The optional browser
companion is documented in `visual-companion.md`; read it only if using that tool.
