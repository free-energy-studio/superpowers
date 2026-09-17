# Free Energy Superpowers for Kimi Code

The inherited `.kimi-plugin/plugin.json` exposes `skills/`, starts with the
`using-superpowers` guidance, and supplies Kimi tool mappings.

Install this fork instead of the upstream marketplace entry:

```text
/plugins install https://github.com/free-energy-studio/superpowers
```

For unmerged work, use the explicit reviewed branch URL rather than assuming the
default branch includes it. Start a new session after changing installed skills.

Inspect `/plugins info superpowers` and the discovered skills to confirm which
checkout is loaded. Check for duplicate local or personal copies of Superpowers.
The internal plugin identifier remains `superpowers` for compatibility.

The manifest maps questions to `AskUserQuestion`, task tracking to `TodoList`,
delegation to `Agent`, and skill loading to `Skill`, when those actions are needed
and the tools are available. Follow the host's actual schema and permission rules.

The local manifest test checks metadata and mapping presence. It does not establish
end-to-end behavior in a live Kimi session.
