# Component authoring and presentation

This is the reuse, implementation, and authoring procedure used by
[enqo-component](../.agents/skills/enqo-component/SKILL.md). Scope, creation, and
publication permissions are defined in [AGENTS.md](../AGENTS.md).
Token coverage is defined in [design-system.md](design-system.md); language and
content previews in [mockup-content.md](mockup-content.md).

## Reuse and platform implementation first

These checks are mandatory before component construction, even when the task
initially asks to build a new component. Work separately for each platform.

1. **Check the existing Enqo design system.** Inspect relevant platform and shared
   sources under [migration rules](figma.md#rules-during-migration), existing usage,
   variants, properties, and slots. Test candidates against the actual requested
   behavior, content, and layout. A supported configuration or composition of
   existing components may already solve the task. If so, tell the designer what
   exists, with exact source names/node URLs/keys and the applicable configuration;
   recommend reuse instead of creating a duplicate. Do not duplicate a fitting
   component merely because the initial task said "build a component".
2. **Always verify the platform-library approach.** Inspect actual project code
   and dependencies/version via [code references](codebases.md), then the matching
   official Flutter API for Mobile or Vuetify API for Web. Entry catalogs:
   [Flutter widgets](https://docs.flutter.dev/ui/widgets) and
   [Vuetify components](https://vuetifyjs.com/en/components/all/). Catalogs are
   discovery links, not evidence of a specific component API or installed version.
   Record the chosen exact symbol/tag, component-specific API URL, version, and
   relevant project wrapper/path/commit. Do this for a reused DS component too;
   a Figma name alone does not establish its implementation.
3. **Prefer the standard solution when no DS candidate fits.** Check whether a
   standard library component, its supported configuration, or a simple
   composition can satisfy the task using existing Enqo tokens. Where a Figma
   representation is missing, identify that gap rather than claim the library
   component already exists in Figma. Creation still follows AGENTS.md.
4. **Use custom work only for an evidenced gap.** If neither DS reuse nor the
   standard library approach supports the requirement, explain the precise
   mismatch and smallest custom addition. Return the actual candidates checked
   and their reasons for rejection. Inaccessible sources or search absence are
   not proof that nothing exists; stop that decision under AGENTS.md. Custom
   creation requires the direct creation instruction; this rule grants no new
   component, token, dependency-installation, or publication permission.

Before writing, report the selected approach and the evidence needed to justify
it, in a short explanation. Do not create a separate research document or generic
comparison matrix for every component.

## Match code and keep the API small

Build the Figma component around the verified Flutter/Vuetify implementation:
functional composition, nested reusable components, slots/content, relevant
properties, state behavior, sizing, and theme/token usage. Use actual project
wrappers when they exist. Document differences and unresolved mappings; visual
similarity does not prove correspondence. Figma layer count need not copy every
code wrapper, but the supported behavior must be implementable with the cited API.

Keep the smallest composition and property/variant set that meets the task.
Allow the supported content and layout variation needed for reuse, through actual
properties/slots rather than duplicated masters for each content example. Do not
add speculative states, configuration knobs, nested wrappers, abstractions, or
variant combinations for imagined future use. Explain a custom wrapper or extra
property through a concrete requirement or verified reuse case. If verified code
or library behavior cannot support the proposed design, report it before building
instead of leaving the developer to invent an implementation.

## Rounded corners

Whenever an authorized component build/edit sets a nonzero corner radius, set
**Corner Smoothing to 60%** on that rounded node. Check every affected rounded
node, not only the outer container, including individually configured corners.
If the node already has 60%, preserve it; if missing, zero, or another value,
set 60% within the authorized edit scope. In the Figma Plugin API this is
`cornerSmoothing = 0.6`, not `60`.
This is a Figma requirement, not a claim of an equivalent Flutter/Vuetify API;
verify implementation support or report a difference under the code-alignment rule.

Keep the corner radius bound to its verified existing token under
[token coverage](design-system.md#required-token-coverage). Smoothing is a separate
parameter with this user-specified value; do not replace the radius, drop its
binding, or invent a smoothing token. This rule does not add rounded corners to
nodes that should remain square.

Read back the actual radius/binding and `cornerSmoothing` after edits and inspect
the rendered result. Reuse alone does not authorize changing shared masters,
detaching nested instances, or altering unrelated nodes to enforce the rule.
If a required change is unsupported or outside the task scope, report the exact
node/property gap and needed change through [harness proposals](harness-proposals.md).

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
   For justified custom work with no existing code symbol, propose the intended
   new code/component name for the naming decision and label it as new. Never
   present that proposal as an existing Flutter/Vuetify or project component.
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
6. Follow [minimal description](#minimal-description) for the visible caption
   inside `Slot`, the actual COMPONENT or COMPONENT_SET's native description,
   and preview labels. Use verified existing typography/color/spacing bindings
   for visible text. Never write a native component description to a frame or
   instance. Report unsupported styling/layout instead of guessing values.

## Minimal description

Apply [mockup-content.md](mockup-content.md) to description language and preview
content, preserving the exact header/component/property identities.

Write for a person or agent who has no original chat. Include text only if it
helps them find, choose, configure, or safely reuse the actual component. This
local format follows [Figma's description guidance](https://help.figma.com/hc/en-us/articles/7938814091287-Add-descriptions-to-styles-components-and-variables)
and adapts [Storybook's agent documentation guidance](https://storybook.js.org/docs/ai/best-practices);
it does not require another documentation tool.

### Visible caption

Inside `Slot`, use 1–2 short sentences: purpose, usage context, and a key behavior
only when useful. The caption may reuse the native description's opening. Keep
the full usage instructions and source references off the presentation frame.

Do not list component counts, icon sizes, paddings, gaps, radii, or layer anatomy
merely because they can be measured. Geometry and tokens belong in actual layout
properties and bindings. Mention a number only when it explains a meaningful
usage constraint or the task explicitly asks for specifications.

### Native description and links

Use the actual main component/set's Description as the reusable entry point,
accessible from instances and Assets. Start with purpose and context in natural
Russian, helping both selection and Figma search; preserve technical names.
Describe common use at set level; variant descriptions add only their relevant
differences instead of repeating the set description.

The minimum is purpose/context and the rule-entry link:
`Перед работой с компонентом прочитай правила: https://github.com/EugeneBondarev/Rulla-design/blob/main/AGENTS.md`.
Add only the following details needed for this component, in short prose or
bullets; this is not a mandatory form:

- **Choice and behavior:** when to use it, an exact linked alternative when the
  distinction matters, and key supported state changes with real property/variant
  names. Never invent standard states.
- **Configuration and limits:** non-obvious property meanings, combinations,
  exact slots/accepted content, allowed overrides, and relevant resizing behavior.
  Include interaction/accessibility expectations when applicable and evidenced;
  a visual example does not prove keyboard or assistive-technology behavior.
- **References and gaps:** exact usage/preview links when available and the
  verified naming/implementation reference from [name and destination](#name-and-destination).
  Link existing sources for longer evidence, using Figma's documentation link
  where supported. Say when usage or mapping is unverified; distinguish intended
  design behavior, implementation, and tested behavior.

Do not dump property types/defaults/value lists, nested-layer inventories, or
token tables already inspectable in the asset unless explaining a necessary
choice. Real properties, slots, instance links, and bindings remain the source
of structural data; prose does not replace them or authorize changing the API.
Report required missing evidence under AGENTS.md and link applicable gaps; do
not guess facts or hide a limitation to keep the description short.

### Examples

Show the main use and materially different supported behavior needed by the task.
Each preview explains one use or change. Use a short Russian label and add a
sentence only for behavior that is not visible. For example, `Выбран жирный текст`
explains the case better than `Пример 2`; this is wording guidance, not a new
state or property name.

Use linked instances with actual property values and the existing
[content-variation checks](mockup-content.md#show-content-variation). Do not create
new masters/variants, every theoretical combination, or repeated measurements for
documentation. Link real output nodes; label illustrative usage as such rather
than claiming an existing product screen or implemented behavior.

Keep component-specific text with the Figma component and previews. No GitHub
page per component, long specification, empty sections, mandatory matrix, or
invented owner. Shared rules stay here; the final chat is not the only documentation.

## Verify and report

Return actual presentation-frame, component/set, `Slot`, and header URLs; source
keys; header headline; naming reference; description; and token-coverage gaps.
Verify the component master is inside `Slot`, the header remains linked, and
source infrastructure is unchanged. Re-read the native description from the
actual component/set and compare it with inspected properties, slots, bindings,
and behavior. Check that captions/preview labels explain use rather than repeat
measurements and that rule/source/preview links resolve. Verify what the available
tool actually returns; visible board text or a link alone does not prove an agent
received its content. The description and inspectable metadata must let the next
agent locate the source, select supported configuration, populate slots, and
understand constraints without the original
chat. Report any unresolved part; do not claim another agent tested it unless
that trial actually occurred. Inspect the rendered frame for fitting
content, readable description, and preserved layout. Report publication separately:
local creation is not publication. Return checked assets and exact links using the
[human-only publication boundary](../AGENTS.md#component-publication-is-human-only).
For an update, give the human a brief summary of changed behavior and any required
instance migration. This complements the description; it grants no publication
permission and does not require a separate release document.
