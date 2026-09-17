# Free Energy Superpowers for OpenCode

The inherited OpenCode adapter registers `skills/` and injects the
`using-superpowers` guidance once into the model-visible message array.
Its local tests check registration, bootstrap loading, and caching.

## Installation

Use this fork instead of upstream. In OpenCode's plugin configuration:

```json
{
  "plugin": ["superpowers@git+https://github.com/free-energy-studio/superpowers.git"]
}
```

Pin a reviewed commit using the Git dependency's `#<commit>` suffix when testing
unmerged work. Upstream tags do not contain Free Energy's changes.

Restart OpenCode and inspect the discovered skills with its native `skill` tool.
Verify that `applying-development-principles` comes from this checkout and that no
second installation supplies competing Superpowers instructions.

If migrating from manually linked skills, inspect the link targets and preserve
personal edits before removing or changing anything. Do not recursively delete a
skills directory based solely on its name.

## Tools and updates

Use the tools actually exposed by the host. The adapter includes mappings for
skill loading, file edits, shell commands, and permitted subagent work; mappings
do not require those actions on every task.

Git dependencies may remain pinned in the host's package cache or lockfile.
Check the resolved revision when updating, rather than assuming restart replaced
the code. For installation failures, consult the host's current diagnostics.

These commands are inherited integration instructions. Local fixture tests are
not proof of a live installation on every OpenCode version.
