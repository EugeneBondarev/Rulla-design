---
name: enqo-flow
description: Compose or refine one Enqo screen, sheet, or multi-screen scenario in Figma from existing verified components and tokens, for Web, Mobile, or both. Use for scenario assembly, not design-system component creation.
---

# Enqo scenario composition

Resolve the shared repository root three directories above this file. Read
[AGENTS.md](../../../AGENTS.md), [Figma map](../../../docs/figma.md),
[screen entry points](../../../docs/scaffolds.md),
[token coverage](../../../docs/design-system.md),
[code references](../../../docs/codebases.md), and
[mockup content](../../../docs/mockup-content.md). Resolve links from this skill,
not an unrelated working directory. Apply AGENTS.md if a dependency is unavailable.

1. Identify the requested outcome, platforms, entry/end actions, destination,
   and authorized operations.
2. Reopen each platform's scaffold and relevant screen sources; inspect the actual
   route and component code. Resolve component source keys/properties/publication
   status, token/style bindings and modes, and the inspected code commit. Use
   this evidence to explain the screen/sheet choice; return the compact source list.
3. Resolve blockers before dependent edits under AGENTS.md. Record token findings
   in [token gaps](../../../docs/token-gaps.md). Apply the scenario boundary;
   do not switch to component work as a workaround.
4. Compose linked instances through supported slots/properties, preserving source
   layout and bindings. Apply mockup-content.md to product copy and visible
   content-length/density cases. Derive states/transitions from the requested
   scenario and actual references/implementation.
5. Verify actual source keys, properties, bindings/modes, layout and text fit,
   requested transitions, and the content cases at required widths. Inspect a
   screenshot of each materially different output; report untested interactions
   and persistence failures under AGENTS.md.
6. Return exact output/case links, source list, checks, and remaining gaps. Record
   concrete harness findings in [proposals](../../../docs/harness-proposals.md)
   using the repository maintenance process. Link saved records or mark drafts
   unsaved; verification of one platform does not establish Web/Mobile parity.
