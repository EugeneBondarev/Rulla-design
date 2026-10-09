---
name: enqo-ds-audit
description: Inspect Enqo Figma assets, Web or Flutter code, and repository instructions for drift and missing evidence. Use for read-only design-system reviews or publication readiness assessments.
---

# Enqo design-system audit

Resolve this file's repository root three directories up. Read
[AGENTS.md](../../../AGENTS.md) and the relevant entries in
[Figma references](../../../docs/figma.md), [scaffolds](../../../docs/scaffolds.md),
[design-system evidence](../../../docs/design-system.md), and
[codebases](../../../docs/codebases.md).

For mockup-content or layout reviews, also read
[Russian mockup content](../../../docs/mockup-content.md).

1. Identify the requested file/node/code scope. Inspect the real sources using
   read-only operations. Leave inspected Figma assets, rules, code, tokens, and
   publication state unchanged. Explicitly requested fixes may change only their
   authorized local assets; publication is always human-only. New component
   creation must be directly specified in the task. Record
   harness proposals and token gaps under the standing authorization in AGENTS.md;
   if the user explicitly prohibits all writes, return the entries as unsaved.
2. Record exact names, source node URLs, keys, properties/variants, bindings,
   publication status, and code paths/commits relevant to each finding. Do not
   treat names, screenshots, search absence, or inaccessible data as proof of
   identity, duplication, deprecation, or missing implementation.
3. Compare only established requirements and mappings. Separate observed
   mismatches from hypotheses and unknowns. Identify the actual task affected by
   each gap; do not invent severity, ownership, or policy.
   Check applicable component and token coverage under AGENTS.md, including raw
   inherited values, actual bindings/modes, and style-to-token mappings. Record
   deficiencies in [token gaps](../../../docs/token-gaps.md), with inspected scope
   and the correct evidence classification. Do not call unverified data missing
   or repair the design system without a direct human request for that repair.
   Within the requested mockup/layout scope, check Russian authored content and
   the visible short/typical/long cases. Preserve exact technical identifiers.
   Report missing cases or observed layout failures with exact nodes and inspected
   widths; do not add preview frames or change UI copy during a read-only audit.
4. Return a table: finding, exact evidence links, task impact, smallest proposed
   correction, and unresolved decision. Include inspected scope and limitations.
5. For each missing or stale instruction, name its destination file and proposed
   exact text, supporting sources, and whether it needs a new human decision.
   Record the concrete bottleneck in
   [harness proposals](../../../docs/harness-proposals.md), following AGENTS.md.
   Do not silently rewrite the standard or claim the correction was applied.
