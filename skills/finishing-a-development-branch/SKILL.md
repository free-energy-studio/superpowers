---
name: finishing-a-development-branch
description: Use when verified changes are ready for the requested commit, pull request, merge, or workspace handoff.
---

# Deliver the Requested Result

Use `verification-before-completion`. Inspect the final diff and working tree,
confirm the branch, remote, and intended base, and preserve unrelated user work.

Follow the already-agreed delivery path. If the user requested a pull request,
open it after the required checks; do not ask them to choose the same action again.
If integration intent is unresolved, ask the one decision needed.

Before pushing or opening a pull request, summarize verification and remaining
risk. Follow the repository's branch protections and review requirements. Do not
merge, release, or deploy merely because implementation was authorized.

A failed check should be explained, not hidden. Do not present work as ready when
required verification failed; a clearly labeled draft handoff can still be useful
if the user wants it.

Do not force-push after rejection without appropriate authorization. Do not infer
workspace ownership from paths such as `.worktrees/`. Keep the branch and checkout
for review iteration unless authorized cleanup is part of the task. Before deleting
anything, resolve the exact target and inspect for work that exists nowhere else.

Finish with the result, relevant link or path, verification, and material limits.
Do not require a fixed menu or a ceremonial handoff checklist.
