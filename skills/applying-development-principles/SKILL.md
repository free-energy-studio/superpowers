---
name: applying-development-principles
description: Use for Free Energy engineering judgment when designing, debugging, implementing, reviewing, or delivering software and agentic systems.
---

# Development Principles

Build the simplest correct, complete solution to the current request.
Simple means fewer concepts and a clear flow, not fewer lines at any cost.

Preserve correct, tested behavior first. Then eliminate duplicated knowledge,
make intent obvious, and use the fewest necessary concepts and moving parts.
Security, privacy, and explicit product requirements constrain these choices.
These principles govern the workflows; they are not an extra step after them.

## Start with what exists

Read the relevant code, contracts, callers, and tests before inventing a pattern.
Reuse established representations and sources of truth. Extend an existing path
when it fits; do not force a bad abstraction just because it already exists.
Prefer modest duplication to coupling things that do not share a real concept.

Distinguish facts from proposals. If the user asks whether a field or mechanism
already exists, inspect it before answering.

## Make additions earn their place

For each new field, layer, dependency, state, or abstraction, ask:
what current requirement needs this, and what breaks without it?

- Do not represent the same fact twice. If an existing tool result records
  completion, do not add a second success/status field with the same meaning.
- Return information a caller needs, not everything an implementation knows.
  Before/after snapshots, revisions, and audit metadata are choices, not defaults.
- Prefer direct code. Extract shared behavior when it removes real duplication
  or expresses a meaningful boundary; do not create a framework for one caller.
- Keep responsibilities coherent. Split by meaning, not line counts or a fixed
  template of controller/service/adapter layers.
- Handle demonstrated failure modes and required guarantees. Do not add queues,
  retries, fallback paths, or extension points for imagined future requirements.

An approval token, permission check, transaction, or idempotency key may be
essential even when it adds code. Judge it by the guarantee it provides, not its
size. Validate untrusted inputs and protect critical invariants at the appropriate
boundary; typed internal helpers need not repeat the same checks.

Harden proactively for security, privacy, permissions, billing, data integrity,
and irreversible effects. For other hardening, require demonstrated risk.
Prefer reversible, observable delivery with a clear rollback. If delivery pressure
conflicts with a safety boundary, narrow, disable, or delay the capability rather
than bypass that boundary.

## Agentic systems

SCENE: shape context and environment, not expression. Give the model accurate,
authorized context, visible state, useful tools, and clear evidence requirements.
Shape semantic behavior there, not through deterministic rewriting, suppression,
retrying, or rerouting of generated meaning.

Use deterministic controls for crisp boundaries: permissions, approvals,
irreversible actions, idempotency, billing, data integrity, and protocol rules.
When a product fact must match authoritative state, render or control it from
typed state rather than asking the model to author it. Post-generation handling
is for mechanical protocol work such as schema validation, encoding, internal
markup containment, and bounded retries for transient failures.

For incorrect model behavior, use the scene-reconstruction method in
`systematic-debugging`; do not compensate for missing context with an output filter.

## Match the task

An explanation needs an answer; an investigation needs evidence; a change needs
implementation and verification. Discussing a design is not permission to build it.
An explicit bounded implementation request does not need another approval of the
same intent. Ask when an unresolved choice materially changes scope or outcome.

Be resourceful within the authorized scope: inspect available evidence and pursue
useful safe checks before escalating. Make the safest narrow assumption when it
does not risk data loss, production impact, or significant rework. Missing authority
or a consequential user choice is a reason to ask, not to improvise permission.

Use only as much planning, documentation, review, and delegation as the work needs.
Do not make users manage your workflow or read a process announcement per step.
Follow repository constraints and higher-priority safety instructions.

These skills guide delegation, not model or provider selection. Leave those
choices to host configuration and explicit user instructions. Platform adapters
translate tool calls; they do not choose models or providers.

For Linear issue work, read [references/linear.md](references/linear.md).
For PR delivery, use `finishing-a-development-branch`. Keep repository-specific
teams, projects, branches, and product rules in the consuming repo's `AGENTS.md`.

## Simplify before handing over

Look at the actual design or diff. What can be removed while preserving the
requirements, readability, and correctness? Remove redundancy, not safeguards.
Do not weaken tests or hide failures to make the implementation look smaller.

When the user corrects an unnecessary pattern, apply that lesson across the
current design, not just to the highlighted field. Explain remaining complexity
only when its concrete purpose matters to the decision.
