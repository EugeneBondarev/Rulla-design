# Component authoring and presentation

This is the presentation/naming procedure used by
[enqo-component](../.agents/skills/enqo-component/SKILL.md). Scope, creation, and
publication permissions are defined in [AGENTS.md](../AGENTS.md).
Token coverage is defined in [design-system.md](design-system.md); language and
content previews in [mockup-content.md](mockup-content.md).

## Exact infrastructure source

Inspected read-only on 2026-10-09 in `🟣 Design System`
(`ig93klQ0XqzeWI1Rm1fHnc`). The user designated this template for presenting new
components. It is library infrastructure, not a product scaffold.

| Role | Exact name and source URL | Observed identity/API |
| --- | --- | --- |
| Page | [Infra, 20597:159663](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=20597-159663) | PAGE |
| Section | [DS Container, 20748:38435](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=20748-38435) | SECTION containing template and header sources |
| Template | [DS Container Template, 20748:37538](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=20748-37538) | COMPONENT; key `ea96507d0ef0939e833406cde3f83cb56be37d09`; SLOT property `Slot#20852:0`; publish status `CHANGED` |
| Header source | [DS header, 20597:159707](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=20597-159707) | COMPONENT; key `a28b136afa3f1508f3db7fdbb50df8a7affc8069`; TEXT property `Headline#20597:0`; publish status `CHANGED` |
| Nested header | [DS header, 20748:37520](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=20748-37520) | INSTANCE linked to the header source above |
| Content | [Slot, 20748:37539](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=20748-37539) | Empty SLOT; expected content FRAME after the user's detach workflow |

The placeholder headline is `Chips & Chips Bar`, not a name for new components.
The template has only the header and empty slot: no separate description text
node or description property exists in this inspected source. The description
below is added to the new detached copy and actual component, not to the template
source. Both sources reported `CHANGED`; a published import may differ from the
exact on-canvas sources. Reopen them and verify the copied revision. Do not
publish the infrastructure or silently substitute a different version.

This inspection did not create or detach anything. Slot conversion and header
preservation are the user-required workflow and must be checked on actual outputs.

## Name and destination

1. Use the exact implemented component name from the relevant
   [Enqo repository](codebases.md) when it exists. Record the repository, path,
   symbol, and inspected commit. Do not rename an existing wrapper to a framework
   primitive because they look similar.
2. Otherwise use the exact platform-library component name: Flutter for Mobile,
   Vuetify for Web. Inspect the project's actual dependency/version and matching
   official API/docs; record the exact symbol/tag, version, and supporting URL.
   Do not invent a name from appearance or a documentation category heading.
3. If no name can be verified or sources conflict, report the naming gap and
   needed decision before naming/creating the component. A similar name does not
   establish a Figma/code mapping.
4. Resolve the destination from the [platform file map](figma.md) and actual
   organization. Record exact file, page, and parent section/frame names and URLs
   before writing. "The correct folder" is not a destination. Report an unresolved
   parent instead of inventing a page or moving unrelated components.

## Place the new component

1. Reopen the exact template, header, properties, layout, and bindings above.
   Create a new instance/copy of that template at the resolved destination.
   Never modify, move, or detach its source component.
2. Detach **only the outer template instance** into an infrastructure frame so
   it can hold component masters. This narrow user-authorized exception applies
   only to this new presentation copy in explicit component authoring. It never
   applies to scenario instances, the header, UI components, or nested instances.
3. Rediscover children after detach rather than reuse invalidated IDs. Verify
   `Slot` is a FRAME and `DS header` remains an INSTANCE linked to the exact header
   key above. If the tool does not preserve this structure, stop and report it;
   do not detach or redraw the header.
4. Place the actual new COMPONENT or COMPONENT_SET inside the resulting `Slot`.
   A preview instance alone is not the component source. Preserve copied layout
   and bindings and the new component's nested instances. Check token coverage;
   record deficiencies in [token gaps](token-gaps.md) without implicit DS repairs.
5. Set the header instance's `Headline#20597:0` to the exact resolved component
   name. Keep the header linked and its master unchanged. Use that name for the
   new component/set and presentation frame; preserve infrastructure child names
   `DS header` and `Slot`. Remove the sample headline from the new copy.
6. Add the minimal visible description inside `Slot`, next to the component in
   the copied layout, with verified existing typography/color/spacing bindings.
   Put the relevant usage contract described below in the actual COMPONENT or
   COMPONENT_SET's native description, accessible without its presentation frame.
   Never write a native description to a frame or instance.
   Report unsupported description styling/layout instead of guessing values.

## Minimal description

Apply [mockup-content.md](mockup-content.md) to description language and preview
content, preserving the exact header/component/property identities.

Design and document the component for the next agent, who has no original chat
context. Consider this while building it, not only when writing the final report.
Keep the description short, but sufficient to explain how to use the actual
component. Include the following only where applicable:

- What the component does and where it is used. Link exact existing usage nodes
  or code when available. If none exists yet, say so and label intended usage as
  proposed; do not invent a screen reference.
- Key supported states, their exact variant/property names, and what changes
  between them. Use inspected code/library behavior or the direct human request;
  never add an imagined standard state checklist.
- How to configure it: relevant property types, actual defaults/allowed values,
  supported combinations, and what each choice changes. Explain semantics that
  are not evident from the exact property name; do not dump every layer or repeat
  machine-readable metadata without adding useful meaning.
- How it is structured: relevant nested component sources and exact slot/layer
  names or node URLs, what content each slot accepts, and which elements an
  instance may override. Preserve the verified API; describing it does not
  authorize adding properties, restructuring masters, or new variants.
- Layout and dependencies: observed resizing/wrapping/truncation behavior,
  applicable constraints, linked token/mode/binding evidence, and required nested
  components. Link actual source nodes or existing records instead of copying a
  token catalog or assuming behavior from appearance.
- Naming source: exact code symbol/path/commit or library API name/version/URL.

Include an actual usage/preview link when available, and state known limitations
or unresolved facts explicitly. Keep component-specific descriptions with the
actual Figma component; do not create a GitHub document per component or rely on
the task's final chat message as its only documentation. No long specification,
empty matrix, invented owner, or speculative behavior is required. Report missing
evidence and needed rule updates through [harness proposals](harness-proposals.md).

## Verify and report

Return actual presentation-frame, component/set, `Slot`, and header URLs; source
keys; header headline; naming reference; description; and token-coverage gaps.
Verify the component master is inside `Slot`, the header remains linked, and
source infrastructure is unchanged. Re-read the native description from the
actual component/set and compare it with inspected properties, slots, bindings,
and behavior. It must let the next agent locate the source, select supported
configuration, populate slots, and understand constraints without the original
chat. Report any unresolved part; do not claim another agent tested it unless
that trial actually occurred. Inspect the rendered frame for fitting
content, readable description, and preserved layout. Report publication separately:
local creation is not publication. Return checked assets and exact links using the
[human-only publication boundary](../AGENTS.md#component-publication-is-human-only).
