# Token gaps

This file owns the token-finding format, evidence classifications, and lifecycle.
Apply [token coverage](design-system.md#required-token-coverage),
[authorization](../AGENTS.md#design-system-changes-require-a-direct-human-request),
and [record-saving rules](../AGENTS.md#maintain-this-repository).

## Current state

Two bounded binding gaps are recorded below. They do not establish coverage
of the rest of the library. Existing inspected bindings are in
[design-system evidence](design-system.md).

## Record a gap

1. Inspect the relevant shared and platform sources from [figma.md](figma.md),
   their actual variables/styles/modes and bindings, and code mappings when the
   task requires them. Record the inspected scope. Inaccessible data or no search
   result does not prove a token is absent.
2. Read existing entries, update the same affected property/role/platform/mode
   instead of duplicating it, and choose the next unused `TG-NNN` ID after refreshing
   `main`. Preserve other agents' additions when resolving changes.
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
| [TG-001](#tg-001--appbutton-disabled-icon-binding) | AppButton S / Secondary Text / Disabled icon fill, Mobile Light | mapping/binding gap | open | 2026-10-13 |
| [TG-002](#tg-002--labelm-font-size-role-binding) | Label/M fontSize binding, Typography Web/Mobile | mapping/binding gap | open | 2026-10-14 |

## TG-001 — AppButton disabled icon binding

**Status / classification / date:** open; mapping/binding gap; 2026-10-13.

**Task and impact:** Creating FormattingOptionsSection from the Mobile toolbar.
The Disabled preview inherited a raw icon color from AppButton. This prevents a
claim of complete token coverage for arbitrary future Disabled configurations;
it did not block creating the requested linked component.

**Target:** Mobile [AppButton](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=22414-4648),
set key `216114b019072ecf8bd31dbb24ed3501478374a0`; variant
[`Type=Secondary Text, Size=S, State=Disabled, Icon only=True`, 22774:5479](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=22774-5479).
Its nested icon 22774:5483 renders vector `I22774:5483;9874:43721` with fill
RGB 0.753000020980835 / 0.7570000290870667 / 0.8270000219345093 and empty
`boundVariables`.

**Discovery:** Inspected AppButton sources, linked formatting buttons, and
Color • Variables in the subscribed shared library. Existing `Icon/Disabled`
has ID `VariableID:292095bb8532ed67b77c9e4a971ac1dcce04ce68/21006:154`,
key `292095bb8532ed67b77c9e4a971ac1dcce04ce68`; Light mode `6398:2`
aliases `VariableID:dad20aa3810422d77ffb6e0dd25068e2c207cc8b/19983:112`.
The token exists; the consuming source binding is absent. Dark output and
other AppButton variants were not exhaustively audited.

**Needed change / acceptance:** A direct request to repair the affected AppButton
source binding, followed by a new icon-swap and Default → Disabled check proving
the correct token is retained. Publication remains human-only.

**Related records:** [HP-005](harness-proposals.md#hp-005--verify-icon-colors-after-button-state-changes).
The direct component-creation request authorized the new local output, not
changes to shared AppButton.

**Resolution:** Shared source remains unresolved and unchanged. Four icon vectors
in the [new code-block preview, 23191:1478](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=23191-1478)
were explicitly bound to Icon/Disabled; bindings were read back. The new
[FormattingOptionsSection, 23191:1386](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=23191-1386)
documents this limitation and remains UNPUBLISHED.

## TG-002 — Label/M font-size role binding

**Status / classification / date:** open; mapping/binding gap; 2026-10-14.

**Task and impact:** Adding the centered Chat Info AppBar example. Reusing
Label/M's binding for a font-size role would propagate a line-height token.
The new example was corrected locally; source-style repair remains outside scope.

**Target and observed state:** Inspected TEXT style Label/M,
ID `S:3ef9f0b8100b4b76eb418500933cc4d1afc4fd3e,20870:9`,
key `3ef9f0b8100b4b76eb418500933cc4d1afc4fd3e`. Its fontSize binding points
to `Font/Line-height/16`, ID
`VariableID:260056e8a3a92ae84696c55f4ee9c17f8445ba10/20501:171`.
Existing usage: [AppBar / Настройки профиля](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=23055-1094),
whose visible title uses Label/M. This is bounded style evidence, not an audit of
all uses.

**Discovery:** The subscribed shared library's Typography collection has the
correct-role `Font/Size/16`, ID
`VariableID:b7dfdd4e1f817e79b94c08f6dfe613aaef8198f7/20501:167`,
key `b7dfdd4e1f817e79b94c08f6dfe613aaef8198f7`; Web mode `19049:0`
is 15, Mobile mode `19050:1` is 16. A matching raw number alone is not a
role-correct mapping.

**Needed decision / acceptance:** Authorize the affected source-style repair and
inspect its consumers and both modes before updating the binding. No new token
is required or proposed.

**Resolution:** Shared Label/M remains unchanged and open. The
[new Chat Info example](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=23321-1330)
uses Heading/S and Caption/M. Its title explicitly binds fontSize to
Font/Size/16, lineHeight to Font/Line-height/22, and the example sets Typography
to Mobile. The binding, 16px size, and global title centering were read back.
