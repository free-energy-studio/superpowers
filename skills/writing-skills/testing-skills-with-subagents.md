# Behavioral Checks for Skills

Use this when a material instruction change needs independent examples.
If subagents are unavailable or prohibited, perform an explicit manual walkthrough
and report that limitation rather than pretending it is independent evidence.

1. Write realistic prompts and expected outcomes before testing. Include a case
   the old instructions mishandle and a safety or scope counterexample.
2. Run baseline prompts against the old instructions where feasible.
3. Give fresh-context agents the revised instructions and the same prompts,
   without revealing the expected answers. Ask for the action or response they
   would produce. For workflow tests, allow a safe fixture when actual execution
   is needed; never point a test at live data.
4. Compare outputs against the expected behavior. Look for both improvement and
   lost safeguards. Revise instructions only when the evidence supports it.
5. Record prompts, relevant instruction revision, observed outcomes, and limits.
   Distinguish a narrated choice from a tool action that actually occurred.

Independent samples and model coverage matter for broad claims. Repeat or expand
tests when results are inconsistent or risk warrants it. A few successful examples
are a useful smoke test, not proof of robust compliance.

Do not reward literal repetition of skill language or compliance with arbitrary
ceremony. Judge the usefulness, correctness, scope, and safety of the result.
