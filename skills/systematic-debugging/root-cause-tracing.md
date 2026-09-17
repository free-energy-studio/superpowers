# Trace the Cause

Start from the observed failure and follow the relevant values and calls backward.
At each step, ask where the assumption became false and what evidence supports it.

For example, a command ran in the source directory because its working-directory
argument was empty. Trace who supplied that value. If a test read a temporary-path
fixture before setup, fix the fixture's lifecycle, then check whether the command
boundary also needs to reject empty paths for other callers.

Use existing traces and logs first. If they are insufficient, add a focused probe
around the uncertain boundary. Record only necessary context; never dump secrets
or whole environments into logs. Distinguish the triggering condition from the
underlying defect and from any incident mitigation.

For test pollution, `find-polluter.sh` can help isolate the responsible test.
Inspect its usage and run it in an appropriate isolated test workspace.

A causal explanation should predict what changes when the fix is applied.
Demonstrate that with a regression test or other discriminating check.
See `defense-in-depth.md` for deciding where validation belongs.
