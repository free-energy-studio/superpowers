# Free Energy Linear Workflow

Read this for Linear issue work or issue-linked delivery, not every development
task. It preserves Free Energy's existing ticket policy; it is not a reason to
invent tickets for unrelated work.

Issue writes need authorization. A read-only investigation does not by itself
authorize creating or updating tickets. When writes are unauthorized or access is
unavailable, give a draft or relationship instructions and state that nothing was
persisted.

## Specification and evidence

- Use sentence-case, action-oriented titles in normal English.
- The issue description is the canonical current specification. Update it when
  requirements, confirmed findings, or the outcome change.
- Use comments for detailed evidence, chronology, progress, implementation plans,
  and reviews. Link the canonical specification rather than copying it into a
  separate spec file.
- When creating an issue-linked branch, use the exact branch name returned by
  Linear. Do not prepend a prefix or reconstruct it. Do not rename an existing
  branch or PR solely for this convention.
- Read the consuming repository's `AGENTS.md` for routing: teams, projects, owners,
  labels, statuses, and product-specific review requirements.

## Reports, investigations, and fixes

When authorized to track a user-affecting report:

1. Keep the incoming report, its investigation, and the fix as distinct records.
   Create a separate investigation per incoming report; do not repurpose the
   report or deduplicate investigations. Start its title with `Investigate` and
   describe the user-facing problem. Relate it to the report.
2. Record the supported causal chain, evidence, affected scope, uncertainty, and
   current outcome. If cause or remedy is uncertain, identify the missing evidence
   and next investigative step.
3. Search for a suitable existing fix by symptom, supported cause, and affected
   component. Reuse and update the canonical fix, link the investigation, and mark
   competing remedy tickets as duplicates. Create a new fix only when a concrete
   remedy is supported and no suitable fix exists; start its title with `Fix`.
4. Put the problem, desired behavior, constraints, and acceptance criteria in the
   fix description, with its implementation plan in a comment.
5. Persist the actual relationships when authorized access is available. Complete
   the investigation only after its evidence, outcome, and relationship to any
   fix are documented.
