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
   For Mobile, perform the [haptic review](../../../docs/scaffolds.md#mobile-haptic-feedback)
   against Apple HIG, the product inventory and actual event call sites before composition.
3. Resolve blockers before dependent edits under AGENTS.md. Record token findings
   in [token gaps](../../../docs/token-gaps.md). Apply the scenario boundary;
   do not switch to component work as a workaround.
4. Arrange the requested flow inside a [scenario section](../../../docs/scaffolds.md#scenario-sections).
   Compose linked instances through supported slots/properties, preserving source
   layout and bindings. Apply mockup-content.md to product copy and visible
   content-length/density cases. Derive states/transitions from the requested
   scenario and actual references/implementation.
   Connect the displayed states using [scenario arrows](../../../docs/scaffolds.md#scenario-connections)
   and their platform/label rules.
   For Mobile, apply [focus and keyboard states](../../../docs/scaffolds.md#mobile-focus-and-keyboard-states)
   before building input states: resolve field focus/cursor, scaffold keyboard
   visibility, input layout, and action configuration from actual sources/code.
5. Verify actual source keys, properties, bindings/modes, layout and text fit,
   requested transitions, and the content cases at required widths. Inspect a
   screenshot of each materially different output; report untested interactions
   and persistence failures under AGENTS.md.
   Verify the section's final margins, fill opacity, and node opacity under its rule.
   Check the scenario connections against the arrow sources and actual transitions.
   For Mobile, verify each haptic marker's exact type, trigger/timing and existing
   versus proposed status under the linked haptic rule; report untested device output.
   Check Mobile keyboard-state evidence and transitions required by that section;
   return actual input/keyboard/action nodes with the state links.
6. Return exact output/case links, source list, checks, and remaining gaps. Record
   concrete harness findings in [proposals](../../../docs/harness-proposals.md)
   using the repository maintenance process. Link saved records or mark drafts
   unsaved; verification of one platform does not establish Web/Mobile parity.
