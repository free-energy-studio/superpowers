# Working on Free Energy Superpowers

This is Free Energy's fork of [obra/superpowers](https://github.com/obra/superpowers).
Keep upstream attribution and the MIT license. Do not submit fork-specific changes upstream.

Read `skills/applying-development-principles/SKILL.md` for the engineering standard.
Keep skills useful, specific, and short. Preserve authorization, user work, and
honest verification; remove process that does not improve the result.

For instruction changes, exercise representative scenarios, including a case where
simplification must not remove a safety check. Record what was actually observed.
For runtime changes, run the relevant integration tests. Do not claim a harness
was tested end-to-end when only its local fixtures ran.

Preserve skill names and plugin identifiers unless a migration is intentional.
Keep bootstrap adapters, supporting prompts, and installation docs consistent.
Use existing tooling; do not add a test framework just to test a prose change.

Work on a topic branch. Open pull requests against this fork's `main`, with the
change, verification, and remaining limitations. Do not merge, publish a release,
or replace someone's installed skills without their authorization.
