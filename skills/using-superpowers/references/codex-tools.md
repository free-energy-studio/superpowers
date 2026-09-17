# Codex Tool Adaptation

Use the tool names and schemas exposed by the current session. They vary between
Codex versions and environments; a static table is not authority over a live schema.

Load skills with the available skill mechanism, or read their `SKILL.md` files.
Use the host's file-editing and execution tools according to its instructions.

When delegation is permitted, give agents bounded tasks and only the context they
need. Use the host's follow-up mechanism for fixes and its completion/wait
mechanism when idle; do not busy-poll.

An existing Codex-managed workspace may already be isolated. Inspect Git state,
preserve user work, and use native workspace controls when appropriate. Do not
infer branch permissions from detached HEAD or a path name.

If an operation is unavailable or blocked, report the precise limitation and a
safe handoff. Do not invent capabilities or ask the user to change configuration
unless the task actually needs it.
