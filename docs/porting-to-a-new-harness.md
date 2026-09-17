# Porting Free Energy Superpowers

Keep the skills shared across hosts. An adapter should expose the same files using
the host's real skill-loading and tool mechanisms, not duplicate the workflow or
introduce new mandatory steps.

## Reuse the closest integration

| Mechanism | Existing examples | Local tests |
| --- | --- | --- |
| Session-start shell hook | Claude-compatible manifest, Cursor, Copilot output shapes | `tests/hooks/` |
| Native skill discovery | Codex, Devin | `tests/codex/`, `tests/devin/` |
| Declared context file | Gemini's `GEMINI.md` | Inspect manifest and live loading |
| Declared startup skill | Kimi | `tests/kimi/` |
| In-process registration and context callback | OpenCode, Pi, Hermes | Corresponding directories in `tests/` |

Inspect the actual adapter and host schema before copying a pattern. Callback
frequency, message shape, and installation semantics differ.

## Preserve these contracts

- Skills remain discoverable and loadable. Bootstrap text, if used, comes from
  `using-superpowers/SKILL.md`; it is guidance, not an instruction-priority override.
- Tool mappings describe available capabilities, not required actions. Do not
  invent delegation, task-list, or file tools when the host lacks them.
- Preserve the host's permissions and the user's configuration. Installation or
  replacement of an existing plugin requires authorization.
- Avoid duplicate context injection. Test repeated callbacks, session transitions,
  and missing-file behavior relevant to the host.
- Keep manifest version fields registered in `.version-bump.json`.
- Preserve platform output shapes. In particular, Codex's empty `hooks` object
  suppresses unintended hook discovery; shell-hook hosts use different JSON keys.
- Retain executable modes and the extensionless shell-hook/polyglot wrapper
  convention where required for Windows dispatch.

## Verify and document

Use local fixtures for registration, payloads, and lifecycle behavior. Before
claiming live support, perform an actual install and session on the target host,
confirm the loaded revision, and record what worked.

Test a realistic ambiguous design request, a clear bounded change, and a scope or
safety boundary. Correct behavior is not mandatory invocation of brainstorming for
every prompt.

Document an installation path that points at this fork, not upstream's official
marketplace. Follow `CLAUDE.md` for contribution and delivery. Do not publish a
release or alter a user's existing installation as an incidental test step.

The longer upstream integration history is available in Git at `b36e082`.
