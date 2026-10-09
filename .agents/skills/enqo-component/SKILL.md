---
name: enqo-component
description: Create, change, or document an Enqo design-system component only when that component work is explicitly requested. Use for source components and their APIs, not ordinary screen or scenario composition.
---

# Enqo component work

Resolve this file's repository root three directories up. Read
[AGENTS.md](../../../AGENTS.md), [Figma references](../../../docs/figma.md),
[component authoring](../../../docs/component-authoring.md),
[design-system evidence](../../../docs/design-system.md), and the relevant
[code references](../../../docs/codebases.md).

1. Identify the direct human component-change request, exact target, and authorized
   properties. A scenario request or recorded defect is not authorization.
   For an additional or new component, creation must be directly specified in the task;
   changing an existing component alone does not authorize new masters or variants.
   For an existing asset, inspect its source node URL, name, key,
   properties/variants, bindings,
   publication status, and linked usage. For a requested new component, label its
   name as new output; first inspect concrete existing reuse candidates. Resolve
   the exact name from project code or the platform library using
   component-authoring.md; do not invent the name or its code correspondence.
2. Inspect the related code file/symbol at a recorded commit when the request
   concerns code alignment. Document correspondence or differences with evidence;
   do not invent props, states, semantic names, or a Code Connect mapping.
3. State the intended component change and affected uses. Resolve required gaps
   using AGENTS.md. Existing task authorization is sufficient for its stated
   edits; expanding to unrelated shared assets needs authorization. Publication
   is always human-only: never publish, even if the task requests publication.
4. Apply only the requested changes, using verified existing tokens/styles unless
   their creation/change was separately included in the request. Preserve native
   instances, supported slots, layout constraints, and unaffected properties.
   Resolve all applicable component/token coverage under AGENTS.md. Report and
   record deficiencies in [token gaps](../../../docs/token-gaps.md); stop edits
   that need missing coverage. Do not extend component authorization into token,
   style, or foundation changes that the human did not request.
   For a requested new component, follow component-authoring.md: copy the exact
   infrastructure template to a verified destination, detach only its outer copy,
   verify the `Slot` frame and linked `DS header`, place the actual component/set
   inside `Slot`, set `Headline#20597:0`, and add the minimal visible and native
   component description. Do not alter the template or detach nested UI instances.
   Do not reorganize existing components unless that work was requested.
5. Check the changed properties/variants, bindings, applicable states, and linked
   usage; inspect the rendered result. Report exact changed node URLs, source
   keys, code references, checks, and publication state. Do not claim publication
   from a successful local edit. Include unresolved coverage and token-gap links;
   inherited raw values and unsupported bindings are not proof of token coverage.
   For a new component, include presentation-frame, Slot, header, and component
   source URLs plus naming evidence and description checks from component-authoring.md.
   Hand the checked local component and exact links to the human for any
   publication; do not trigger publication through tools or delegate it to agents.
6. Propose the exact documentation diff for a verified new fact or missing rule.
   Record observed harness bottlenecks in
   [harness proposals](../../../docs/harness-proposals.md), following AGENTS.md.
   Keep proposed conventions separate from human-approved decisions.
