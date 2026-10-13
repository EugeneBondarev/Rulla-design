---
name: enqo-ds-audit
description: Inspect Enqo Figma assets, Web or Flutter code, and repository instructions for drift and missing evidence. Use for read-only design-system reviews or publication readiness assessments.
---

# Enqo design-system audit

Resolve the shared repository root three directories above this file. Read
[AGENTS.md](../../../AGENTS.md) and relevant sources in
[Figma map](../../../docs/figma.md), [entry points](../../../docs/scaffolds.md),
[token coverage](../../../docs/design-system.md), and
[codebases](../../../docs/codebases.md). For component presentation or mockup/layout
reviews, also read [component authoring](../../../docs/component-authoring.md)
and [mockup content](../../../docs/mockup-content.md).

1. Identify the exact audit scope. Inspect sources read-only under AGENTS.md;
   findings do not grant permission to repair assets. Apply its record-saving
   authorization and any explicit all-writes prohibition.
2. Capture finding-specific names/node URLs/keys, properties, bindings/modes,
   publication status, and code paths/commits. Compare only established requirements
   and mappings; distinguish observations, hypotheses, and unknowns.
3. Within the requested scope, check applicable token coverage, component
   presentation, Russian content, and visible content cases against their topic
   documents. Identify missing cases, unverified evidence, and observed failures
   with exact nodes/properties/widths. Do not create missing previews during review.
4. Return a table of findings, evidence, actual task impact, smallest proposed
   correction, and needed decision, plus inspected scope and limitations.
5. Record token deficiencies in [token gaps](../../../docs/token-gaps.md) and broader
   bottlenecks in [proposals](../../../docs/harness-proposals.md). For a missing or
   stale rule, identify its existing home and exact proposed correction/source;
   apply repository maintenance in AGENTS.md. Do not report a proposal as applied.
