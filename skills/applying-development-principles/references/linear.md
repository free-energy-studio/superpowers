# Linear workflow

Use the separately installed `linear` skill for Linear planning, issue hygiene,
reports/investigations/fixes, and issue-linked branches and PRs. It owns the shared
rules; this reference is a compatibility entry point, not another policy copy.
Load it only for Linear work or issue-linked delivery.

The skill's source is
[`free-energy-studio/skills/linear`](https://github.com/free-energy-studio/skills/tree/d25d580dfab47664391a8d7f1724982b93f479cd/linear).
Use this pinned revision through the consuming project's skill manager so the
dependency includes the consolidated policy before its source PR lands.
Read the consuming project's `AGENTS.md` and `docs/linear/` for workspace, routing,
and product-specific review requirements.

If `linear` is missing, report the dependency and provide a draft rather than
inventing policy or persisting issue changes. Install it through the consuming
project's skill-management workflow when installation is authorized. Do not copy
its rules into this fork.
