---
name: enqo-component
description: Create, change, or document an Enqo design-system component only when that component work is explicitly requested. Use for source components and their APIs, not ordinary screen or scenario composition.
---

# Enqo component work

Resolve the shared repository root three directories above this file. Read
[AGENTS.md](../../../AGENTS.md), [Figma map](../../../docs/figma.md),
[component authoring](../../../docs/component-authoring.md),
[token coverage](../../../docs/design-system.md),
[mockup content](../../../docs/mockup-content.md), and relevant
[code references](../../../docs/codebases.md).

1. Identify the direct human request, exact target, and authorized properties;
   apply the creation and publication boundaries in AGENTS.md. Inspect an existing
   asset's source URL/name/key, properties/variants, bindings, publication status,
   and linked usage.
2. Before construction, follow
   [reuse and platform checks](../../../docs/component-authoring.md#reuse-and-platform-implementation-first).
   Report fitting DS assets to the designer; verify the actual Flutter/Vuetify
   approach and project code/version, then justify reuse, a standard solution,
   or the smallest custom addition. Resolve naming/destination and prerequisites.
3. Apply only the authorized changes and the token-coverage procedure. For a new
   component, follow component-authoring.md for the exact infrastructure source,
   outer-copy detach, Slot/header structure, naming, and the
   [minimal description format](../../../docs/component-authoring.md#minimal-description).
   Apply its code-alignment and small-API rules, and mockup-content.md to visible
   content cases; preserve unaffected assets.
   When setting corner radii, apply [rounded corners](../../../docs/component-authoring.md#rounded-corners)
   and read back the actual smoothing value and preserved radius binding.
4. Check changed properties/variants, bindings/modes, applicable states, usage, and
   rendered content cases. For a new component, return the presentation/Slot/header
   and component URLs, naming evidence, and description checks specified in
   component-authoring.md. Hand the checked local assets and observed publication
   state to the human under AGENTS.md; do not infer publication from a local edit.
   Read back the caption, native Description/links, and preview labels; apply the
   [handoff check](../../../docs/component-authoring.md#verify-and-report) against
   the actual source/API and what the available tool returns.
5. Return code evidence, checks, and unresolved gaps. Record token deficiencies in
   [token gaps](../../../docs/token-gaps.md), concrete harness bottlenecks in
   [proposals](../../../docs/harness-proposals.md), and verified documentation
   corrections through the repository maintenance process. Link actual saved
   records; keep proposals distinct from adopted decisions.
