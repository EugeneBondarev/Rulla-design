---
name: enqo-flow
description: Compose or refine one Enqo screen, sheet, or multi-screen scenario in Figma from existing verified components and tokens, for Web, Mobile, or both. Use for scenario assembly, not design-system component creation.
---

# Enqo scenario composition

Resolve this file's repository root three directories up. Read
[AGENTS.md](../../../AGENTS.md), [Figma references](../../../docs/figma.md),
[scaffolds](../../../docs/scaffolds.md), and
[design-system evidence](../../../docs/design-system.md). Use paths relative to
this skill, not an unrelated current working directory. If the shared repository
is unavailable, report that missing prerequisite; do not substitute general advice.

1. Extract the requested outcome, platform(s), entry action, end condition, and
   authorized Figma destination. Resolve missing references with tools first.
2. For each platform, reopen the exact source scaffold and relevant existing
   screen. Read the corresponding route and component code via
   [codebases](../../../docs/codebases.md). A page called Templates is not a
   verified template; an instance called Scaffold does not identify its source.
3. Before writing, return a compact source list: exact scaffold/component names,
   source node URLs, keys, selected properties/variants, exact token/style
   identities and bindings, reference screen URLs, and inspected code commit.
   Explain the screen/sheet choice using that evidence. Do not infer canonical
   status or a one-to-one code mapping from names.
4. Apply the missing-evidence procedure in AGENTS.md to unresolved dependencies.
   State the file and exact documentation text needed to unblock the choice.
   Do not create a new DS asset as a workaround or invoke enqo-component silently.
5. Compose the authorized screen(s) with native linked instances and supported
   slots/properties. Preserve source bindings and layout constraints. New output
   names and task-specific copy are allowed; they are not existing standards.
6. Derive the state/transition list from the requested scenario, linked references,
   and current implementation. Flag conflicts or requirements that are not
   established. Do not add speculative product behavior to fill a checklist.
7. Verify actual instance source keys, property values, variable/style bindings,
   applicable modes, layout/text fit, and requested transitions. Inspect a
   screenshot of each materially different output. Report untested interactions
   and persistence failures without claiming completion for them.
8. Return linked output names, source list, performed checks, remaining gaps, and
   any exact documentation update proposed. Do not claim Web/Mobile parity from
   verification of only one platform.
