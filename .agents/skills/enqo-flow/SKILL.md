---
name: enqo-flow
description: Compose or refine one Enqo screen, sheet, or multi-screen scenario in Figma from existing verified components and tokens, for Web, Mobile, or both. Use for scenario assembly, not design-system component creation.
---

# Enqo scenario composition

Resolve this file's repository root three directories up. Read
[AGENTS.md](../../../AGENTS.md), [Figma references](../../../docs/figma.md),
[scaffolds](../../../docs/scaffolds.md), and
[design-system evidence](../../../docs/design-system.md) and
[Russian mockup content](../../../docs/mockup-content.md). Use paths relative to
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
   status or a one-to-one code mapping from names. Resolve applicable color,
   typography, spacing, size, radius, and effect coverage as required by AGENTS.md,
   including source-inherited bindings and actual modes. A style or raw value
   without verified token mapping is not complete coverage.
4. Apply the missing-evidence procedure in AGENTS.md to unresolved dependencies.
   State the file and exact documentation text needed to unblock the choice.
   Do not create a new DS asset as a workaround or invoke enqo-component silently.
   New components require a direct creation instruction; ordinary scenario work
   permits existing-component instances only. Never publish components or updates;
   publication is exclusively a human action.
   Report and save each token deficiency in
   [token gaps](../../../docs/token-gaps.md), distinguishing confirmed absence,
   unknown evidence, mapping/binding gaps, and tool limitations. Stop the affected
   edit; no temporary hardcoding or shared-source repair is authorized by a flow.
5. Compose the authorized screen(s) with native linked instances and supported
   slots/properties. Preserve source bindings and layout constraints. New output
   names and task-specific copy are allowed; they are not existing standards.
   Author Russian user-facing content and show distinct realistic short, typical,
   and long cases for the content-bearing layouts under mockup-content.md.
   Preserve exact technical names and vary content without creating DS variants
   or inventing unsupported product states.
6. Derive the state/transition list from the requested scenario, linked references,
   and current implementation. Flag conflicts or requirements that are not
   established. Do not add speculative product behavior to fill a checklist.
7. Verify actual instance source keys, property values, variable/style bindings,
   applicable modes, layout/text fit, and requested transitions. Inspect a
   screenshot of each materially different output. Report untested interactions
   and persistence failures without claiming completion for them. Recheck coverage
   on composed containers/text and instance overrides as well as source components;
   do not claim full token coverage with unresolved required properties.
   Inspect each shown content-length/density case at the required platform widths
   for wrapping, overflow, alignment, and supported scrolling/truncation. Return
   exact case/output links and remaining content gaps. Do not hide failures by
   shortening examples or overriding typography/tokens.
8. Record observed harness bottlenecks in
   [harness proposals](../../../docs/harness-proposals.md), following AGENTS.md.
   Return linked output names, source list, performed checks, remaining gaps, and
   recorded proposal/token-gap links or explicitly unsaved entries. Do not claim
   Web/Mobile parity from verification of only one platform.
