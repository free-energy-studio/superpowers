# Free Energy Superpowers

A fork of [obra/superpowers](https://github.com/obra/superpowers) for simple,
essential software development: fewer concepts, clear contracts, and no redundant
code or workflow.

## What changes

The engineering standard is
[applying-development-principles](skills/applying-development-principles/SKILL.md):
start with existing code, make new concepts earn their place, and simplify before
handing work over.

Free Energy's formerly separate development-principles guidance is consolidated
here. Engineering judgment lives in that core skill, causal and model-context
investigation in `systematic-debugging`, Linear policy in its
[optional reference](skills/applying-development-principles/references/linear.md),
and PR policy in `finishing-a-development-branch`. Principles govern the workflows,
not an additional process layer.

We preserve evidence-based debugging, meaningful tests, honest verification,
useful review, and safeguards for user work and permissions. We change the defaults:

- Skills apply to the actual task, not every conversational turn.
- Clear implementation requests proceed without re-approving the same intent.
- Plans capture decisions and dependencies, not a second copy of the code.
- Shared abstractions and defensive checks need a concrete purpose.
- Test-first is preferred; working code is not discarded to enforce chronology.
- Review and delegation scale with risk and useful parallelism, without
  prescribing models or providers.
- Delivery follows the user's instructions instead of a fixed menu.

See the [behavioral checks](tests/free-energy/scenarios.md) for examples and scope
of validation. This is not a claim that prompting eliminates overengineering.

## Use this fork

Install this fork **instead of**, not alongside, upstream Superpowers. Skill names
and the internal plugin identifier remain `superpowers` for compatibility.
Check for repository-local or personal copies of the same skills: those can still
supply the old instructions even after a plugin is replaced.

Install the complete `skills/` tree: all 15 skills, including
`applying-development-principles`. The workflows depend on that bundled core;
do not omit it when removing the old standalone principles skill. For vendored
installations, update their recorded source/revision as well as the files.
Repository-specific rules remain in the consuming repo's `AGENTS.md`.

The existing `gh-coderabbit-review-loop` integration remains separately installed
where required; this consolidation preserves the review policy without copying
the bot's mechanics into the core. A missing required integration must be reported,
not silently treated as a completed review.

This repository retains upstream's platform adapters. The fork is not published
in upstream's official marketplaces. Point your supported plugin/skill loader at
a checkout of this repository, or use its Git-repository install flow with
`https://github.com/free-energy-studio/superpowers`.

The Codex plugin is described in `.codex-plugin/plugin.json`, with the repository
marketplace at `.agents/plugins/marketplace.json`. Claude-compatible metadata is
in `.claude-plugin/`. Other inherited adapters remain in their platform folders.
See [OpenCode](docs/README.opencode.md) and [Kimi](docs/README.kimi.md) for their
repository-based installation paths.

Use a reviewed commit or branch for unreleased changes. Existing upstream tags
refer to upstream releases, not the Free Energy changes. Start a new agent session
after changing installed instructions.

No installation is modified merely by cloning this repo.

## Development

Read [CLAUDE.md](CLAUDE.md) (also exposed as `AGENTS.md`).
Verification commands and limitations are in [docs/testing.md](docs/testing.md).
Contribute through a topic branch and a pull request against this fork's `main`.

Historical design documents under `docs/plans/` and `docs/superpowers/`, including
retired instruction examples in `docs/superpowers/history/`, describe upstream
decisions. They and the upstream release notes are not the current workflow and
are not part of the shipped skill tree. The active skills and their linked
references are the current guidance.

## Attribution

Based on Superpowers v6.3.0, upstream commit `b36e082`, by Jesse Vincent and
contributors. Original history, helpers, platform integrations, and the
[MIT license](LICENSE) are retained. Free Energy maintains the fork-specific changes.
