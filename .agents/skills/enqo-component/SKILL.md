---
name: enqo-component
description: Create, change, or document an Enqo design-system component only when that component work is explicitly requested. Use for source components and their APIs, not ordinary screen or scenario composition.
---

# Enqo component work

Resolve this file's repository root three directories up. Read
[AGENTS.md](../../../AGENTS.md), [Figma references](../../../docs/figma.md),
[design-system evidence](../../../docs/design-system.md), and the relevant
[code references](../../../docs/codebases.md).

1. Identify the explicit component request and exact target. For an existing
   asset, inspect its source node URL, name, key, properties/variants, bindings,
   publication status, and linked usage. For a requested new component, label its
   proposed name as new; first inspect concrete existing reuse candidates.
2. Inspect the related code file/symbol at a recorded commit when the request
   concerns code alignment. Document correspondence or differences with evidence;
   do not invent props, states, semantic names, or a Code Connect mapping.
3. State the intended component change and affected uses. Resolve required gaps
   using AGENTS.md. Existing task authorization is sufficient for its stated
   edits; publishing or expanding to unrelated shared assets needs authorization.
4. Apply only the requested changes, using verified existing tokens/styles unless
   their creation/change was separately included in the request. Preserve native
   instances, supported slots, layout constraints, and unaffected properties.
5. Check the changed properties/variants, bindings, applicable states, and linked
   usage; inspect the rendered result. Report exact changed node URLs, source
   keys, code references, checks, and publication state. Do not claim publication
   from a successful local edit.
6. Propose the exact documentation diff for a verified new fact or missing rule.
   Record observed harness bottlenecks in
   [harness proposals](../../../docs/harness-proposals.md), following AGENTS.md.
   Keep proposed conventions separate from human-approved decisions.
