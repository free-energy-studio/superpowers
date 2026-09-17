---
name: applying-development-principles
description: Use when designing, implementing, refactoring, or reviewing software to choose the simplest correct solution to the current requirements.
---

# Development Principles

Build the simplest correct, complete solution to the current request.
Simple means fewer concepts and a clear flow, not fewer lines at any cost.

## Start with what exists

Read the relevant code, contracts, callers, and tests before inventing a pattern.
Reuse established representations and sources of truth. Extend an existing path
when it fits; do not force a bad abstraction just because it already exists.

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

## Agentic systems

When model behavior is wrong, inspect the context, tools, and evidence it actually
received. Supply missing state at the source. Use deterministic controls for crisp
boundaries such as permissions and approvals; do not add semantic output rewriting
or retry loops to compensate for an underspecified model-visible situation.

## Match the task

An explanation needs an answer; an investigation needs evidence; a change needs
implementation and verification. Discussing a design is not permission to build it.
An explicit bounded implementation request does not need another approval of the
same intent. Ask when an unresolved choice materially changes scope or outcome.

Use only as much planning, documentation, review, and delegation as the work needs.
Do not make users manage your workflow or read a process announcement per step.
Follow repository constraints and higher-priority safety instructions.

## Simplify before handing over

Look at the actual design or diff. What can be removed while preserving the
requirements, readability, and correctness? Remove redundancy, not safeguards.
Do not weaken tests or hide failures to make the implementation look smaller.

When the user corrects an unnecessary pattern, apply that lesson across the
current design, not just to the highlighted field. Explain remaining complexity
only when its concrete purpose matters to the decision.
