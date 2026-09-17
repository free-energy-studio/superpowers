# Review Prompt

Provide the reviewer with:

- The requested outcome and canonical requirements.
- The checkout and exact diff/commit range.
- Relevant constraints and known uncertainties.
- Verification results and what was not tested.

Ask:

> Review this change read-only for correctness, scope, integration, and necessity.
> Inspect relevant callers or tests when needed to judge a concrete risk.
> Check the implementation against the requirements and test evidence.
> What added concepts or code could be removed without losing required behavior?
> Do not propose speculative features or treat stylistic preferences as blockers.
> Do not edit the checkout or dispatch more agents.
>
> Return actionable findings with file/line, the triggering case, impact, and
> suggested correction where clear. Distinguish blockers from optional suggestions.
> If there are no findings, say so and name material verification gaps.
> Review approval does not authorize merging.

Run additional checks when they answer an unresolved correctness question.
Do not rerun tests solely to reproduce already-valid evidence, but do not treat an
implementer's report as proof when it is inconsistent with the diff.
