# Design-system evidence

The reuse and no-invention policy lives in [AGENTS.md](../AGENTS.md). This file
contains inspected token evidence, not a speculative catalog of semantic roles.

Component presentation, code/library naming, minimal descriptions, and the exact
infrastructure template are defined in [component-authoring.md](component-authoring.md).
Use it with enqo-component for directly requested component work.

## Verify coverage for the requested output

Before dependent edits, resolve coverage for the applicable properties required
by [AGENTS.md](../AGENTS.md). For each source component or newly composed layout,
record its exact node URL and property, component key where applicable, actual
variable/style name and ID/key, collection, effective mode, aliases, and consuming
binding. Group properties only when they share the same verified evidence.

An inherited binding counts when its source and selected mode are verified. A
text/effect style needs a verified token mapping for its applicable properties;
its name alone is insufficient. A hardcoded source value, similar appearance,
or matching numerical value does not establish token coverage. Do not modify a
master to fix uncovered properties during scenario work.

Verify bindings again on the output, including instance overrides and composed
containers/text. Report checked scope and unresolved properties explicitly.
Record missing tokens, unknown coverage, missing mappings, and binding limitations
in [token-gaps.md](token-gaps.md), using its distinct evidence classifications.
This checklist does not declare a global token inventory or complete coverage.

The approved target file organization and current migration state are in
[Figma references](figma.md). Shared
foundations remain in `🟣 Design System`; platform components are moving to the
Web and Mobile files. This target does not resolve every per-token code mapping
or make a remaining component in the historical file obsolete.

## Existing repository tokens

[tokens/typography.json](../tokens/typography.json) was copied byte-for-byte from
[Enqo.Design at 63c34913](https://git.aimadev.space/platform/Enqo.Design/-/blob/63c349132255892fcb857652774053fc204de452/tokens/typography.json). It contains
`primitives.font` and `Typography/Mobile`; for example the exact token path
`Typography/Mobile.Body.M` references `primitives.font.size.16` and
`primitives.font.lineHeight.22`.

The file's existence does not establish current Figma bindings, Web coverage,
deployment, or automatic synchronization. No verified export/import pipeline or
cross-system token mapping is registered here. Do not overwrite Figma variables
from this JSON or declare it the global token authority without that evidence.

## Observed Web Sheet bindings

Read 2026-10-09 from [Sheet, 24227:16](https://www.figma.com/design/nOYabg1FJaeMH7iUe2QRdi?node-id=24227-16).
All rows link to the actual consuming node; variable keys identify remote assets.

| Bound property | Exact variable name | Exact collection | Variable key | Collection modes |
| --- | --- | --- | --- | --- |
| Fill color | Surfaces/Default Card Level | Color • Variables | `145acdfb9862052587d78ee72a19b7b4e273dba8` | Light, Dark |
| All four paddings | 3 | Spacing • Aliases | `cbc5ec5d2bd9b1ad72f3109e8cb92dcd3fed1c81` | Web, Mobile |
| All four corner radii | Corner Radius/M | Numbers • Aliases | `8f89499f9b7d99673818785364a30d65da558ae1` | Web, Mobile |

These bindings describe this node; they are not defaults for every screen. Mode
existence does not prove a task's mode selection. Resolve the target's inherited
and explicit modes, values/aliases, and exact text/effect styles before changing
them. Preserve bindings when composing instances. Do not replace variable `3`
with a made-up semantic name or guess its numerical value.

## Missing evidence to resolve per task

- The chosen screen's complete component/style/token inventory: inspect only the
  assets needed for the requested scenario, with exact names and references.
- Figma-to-Web/Flutter token mappings and canonical token ownership: compare the
  actual bindings with the revision-linked [code sources](codebases.md), then
  propose the specific mapping and any owner decision. No global mapping is
  implied by this starter.
- States, layout constraints, and screen/sheet selection: cite an existing
  scenario, implementation, or approved decision for each applicable behavior.
  Do not manufacture an offline/loading/error state merely to fill a checklist.

For an explicit DS change, document the changed source asset, exact properties,
bindings, applicable state behavior, linked usage, code relationship, and observed
publication status. Scenario composition does not authorize those DS changes.
