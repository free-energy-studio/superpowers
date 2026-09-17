# Validation at Meaningful Boundaries

Validate where untrusted or unvalidated data enters, and enforce critical invariants
where the protected effect occurs. Multiple checks are useful when they cover
different bypass paths, not merely because there are multiple functions.

For an invalid value that passed through the system:

1. Trace where it originated and which callers can reach the mutation.
2. Find the boundary that should establish its validity for those callers.
3. Reuse the schema or validator there. Let trusted internal helpers consume the
   validated value rather than rechecking it mechanically.
4. Test the failing entry path and any distinct bypass that matters.

For example, if an HTTP schema validates a mode but a background job bypasses it,
cover the job's input boundary or a shared mutation boundary. Do not add the same
enum check to every internal helper.

Authorization at execution time, database constraints, and environment safeguards
can protect independent guarantees. Keep them when needed. Type annotations alone
do not validate untrusted runtime data; conversely, not every internal call is a
new trust boundary.

Diagnostics help explain failures but do not prevent them. Add logging to answer
a concrete question, avoid sensitive data, and remove temporary noise afterward.
