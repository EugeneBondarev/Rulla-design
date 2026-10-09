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
   and linked usage. For a requested new component, inspect actual reuse candidates
   and resolve its naming source and destination through component-authoring.md.
2. When code alignment is requested, inspect the relevant file/symbol at a recorded
   commit. Describe established correspondence and differences. State the intended
   change and affected uses; resolve missing prerequisites under AGENTS.md.
3. Apply only the authorized changes and the token-coverage procedure. For a new
   component, follow component-authoring.md for the exact infrastructure source,
   outer-copy detach, Slot/header structure, naming, and descriptions. Apply
   mockup-content.md to visible content cases; preserve unaffected assets.
4. Check changed properties/variants, bindings/modes, applicable states, usage, and
   rendered content cases. For a new component, return the presentation/Slot/header
   and component URLs, naming evidence, and description checks specified in
   component-authoring.md. Hand the checked local assets and observed publication
   state to the human under AGENTS.md; do not infer publication from a local edit.
   Re-read the component's native usage description and verify its agent-handoff
   check in component-authoring.md against the actual source/API.
5. Return code evidence, checks, and unresolved gaps. Record token deficiencies in
   [token gaps](../../../docs/token-gaps.md), concrete harness bottlenecks in
   [proposals](../../../docs/harness-proposals.md), and verified documentation
   corrections through the repository maintenance process. Link actual saved
   records; keep proposals distinct from adopted decisions.
