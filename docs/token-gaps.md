# Token gaps

This file owns the token-finding format, evidence classifications, and lifecycle.
Apply [token coverage](design-system.md#required-token-coverage),
[authorization](../AGENTS.md#design-system-changes-require-a-direct-human-request),
and [record-saving rules](../AGENTS.md#maintain-this-repository).

## Current state

No token-gap entries have been recorded yet. This does not establish complete
coverage: this documentation change did not audit Figma or implementation tokens.
Existing inspected bindings are in [design-system evidence](design-system.md).

## Record a gap

1. Inspect the relevant shared and platform sources from [figma.md](figma.md),
   their actual variables/styles/modes and bindings, and code mappings when the
   task requires them. Record the inspected scope. Inaccessible data or no search
   result does not prove a token is absent.
2. Read existing entries, update the same affected property/role/platform/mode
   instead of duplicating it, and choose the next unused `TG-NNN` ID after fetching
   the current branch. Preserve other agents' additions when resolving changes.
3. Classify the evidence separately from the lifecycle status:
   - `confirmed missing`: inspection of the relevant available sources establishes
     that no existing token supports the required property and role in this scope.
   - `unverified`: required sources or bindings could not be inspected; existence
     or suitability remains unknown.
   - `mapping/binding gap`: an existing token/style is identified, but the
     required consuming binding or Figma/code mapping is absent or unverified.
     State which fact is observed and which remains unknown.
   - `unsupported binding`: the required property cannot use the intended binding
     through the available tool/API; cite the observed limitation.
4. Use the fields below with exact references. If a required identity is unknown,
   say so and record where discovery stopped. Never invent a source URL, token
   name, component, owner, or approved replacement. Describe the needed role using
   the actual task and property; a matching raw value is not a semantic mapping.
5. Start with lifecycle `open`. Use `deferred` only with a linked human decision.
   Use `resolved` only with actual resolution evidence and a check of the affected
   property, mode, and binding. Token creation or other DS repair also needs the
   direct human authorization reference. Keep the original evidence and history.
6. Save and report under [repository maintenance](../AGENTS.md#maintain-this-repository),
   including the entry link, blocked action, and specific decision/source needed.

Use [harness proposals](harness-proposals.md) for systemic improvements; link the
`TG-NNN` entry there instead of keeping competing token-gap records.

## Entry fields

This is the entry format, not an assertion that any token is missing. For each
real finding, add a `TG-NNN` section and an index row with a link to that section.

- **Status, evidence classification, date:** actual lifecycle, classification
  above, inspection date; explicit unknowns.
- **Task and impact:** requested scenario, required visual role, affected action,
  and what cannot be completed with verified coverage.
- **Target:** Web/Mobile, exact Figma file and consuming node name/URL, property,
  source component name/node URL/key when inherited, collection and effective
  mode(s). For code-only findings, exact repository/file/symbol/commit and property;
  identify any unresolved Figma counterpart instead of inventing it.
- **Observed state:** actual value, style or variable identity/key and binding,
  whether inherited or overridden, mode/alias resolution; distinguish a raw value
  from a token. Include evidence links or an exact tool observation.
- **Discovery:** inspected libraries/collections/styles and exact search terms;
  relevant existing candidates and evidence-backed reason each does not satisfy
  this property/role/mode. Record access or tool limitations.
- **Needed decision or change:** precise missing evidence or requested DS work,
  affected source, and acceptance check. No fabricated future token standard.
- **Related records:** existing `TG-NNN`, `HP-NNN`, task/PR, and human decision
  references when present. Do not invent links for unavailable records.
- **Resolution:** initially unresolved; later link the authorization where needed,
  changed source/output, exact resulting token and binding, and observed check.

## Index

| ID | Target property and platform/mode | Evidence classification | Status | Date |
| --- | --- | --- | --- | --- |
