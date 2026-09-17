# Testing Free Energy Superpowers

Test runtime behavior and instruction behavior separately. Neither substitutes
for the other.

## Local integration checks

Run from the repository root with Bash, Python 3, Node (for the inherited
Node test suites), and the dependencies required by the selected tests.
Hermes tests require `pytest`.

```bash
bash tests/hooks/test-session-start.sh
bash tests/codex/test-marketplace-manifest.sh
bash tests/codex/test-package-codex-plugin.sh
bash tests/codex-plugin-sync/test-sync-to-codex-plugin.sh
bash tests/opencode/run-tests.sh
node --test tests/pi/test-pi-extension.mjs
python3 -m pytest tests/hermes -q
bash tests/kimi/test-plugin-manifest.sh
bash tests/devin/test-devin-plugin.sh
bash tests/antigravity/test-antigravity-tools.sh
git diff --check
```

The Codex archive test packages committed HEAD, not dirty working files. Commit
the candidate first when verifying new manifests or skills. Its metadata fixture
tests archive construction; it does not publish a release or validate an official
marketplace submission.

Portal packaging still requires external `agents/openai.yaml` metadata for every
skill. An upstream package cannot supply metadata for the new
`applying-development-principles` skill; a fork-specific metadata source is needed
before producing that release artifact. Checkout-based plugin installs do not
depend on this packaging path. No portal artifact is published by this change.

OpenCode's default runner uses local fixtures; `--integration` additionally needs
a live OpenCode installation. The Pi and Hermes suites simulate host callbacks.
Manifest checks verify the declared wiring, not a live model session.

Run helper-specific suites when changing those helpers: brainstorm-server tests,
`tests/systematic-debugging/`, `tests/writing-skills/`, and the SDD workspace script
test. Runtime helpers are retained from upstream, not redesigned by this fork.

## Skill behavior

[tests/free-energy/scenarios.md](../tests/free-energy/scenarios.md) records the
motivating examples, expected behavior, and the initial baseline/revised smoke
results. Use fresh-context agents when available and permitted. Test consequential
decisions, including preservation of authorization boundaries, not literal wording.

The inherited LLM suites under `tests/claude-code/` and
`tests/explicit-skill-requests/` encode upstream workflow expectations. They are
historical references, not this fork's acceptance criteria. Some assert mandatory
worktrees, review ordering, or skill invocations that this fork intentionally removes.
The helper script tests in those directories can still be relevant independently.

The upstream external `evals/` harness is not included. No full cross-model or
live cross-harness behavioral validation is claimed.

## Initial verification

On 2026-09-17 the revised instructions passed the nine narrated scenario checks
with the limitations recorded beside them. All 15 skill frontmatters were validated
using the skill-authoring validator. Local integration results are recorded on the
change's pull request; consult that evidence for the exact tested revision.
