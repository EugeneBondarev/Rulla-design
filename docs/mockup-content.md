# Russian content and layout checks

This rule applies to Web and Mobile scenarios and component work. The user
specified Russian as the main mockup language on 2026-10-09. The authorization,
component-reuse, token-coverage, and human-only publication rules in
[AGENTS.md](../AGENTS.md) still apply.

## Language and realistic content

All authored user-facing mockup content must be in Russian: headings, labels,
buttons, placeholders, descriptions, messages, list/card content, and supported
empty/error states. Visible explanatory notes and component descriptions must
also be in Russian. Never leave English sample UI copy or lorem ipsum in an output.

Preserve exact technical identities: component names from code/Flutter/Vuetify,
variant/property names, token names, node references, paths, and URLs. The
component header required by [component authoring](component-authoring.md) keeps
the exact component name; its explanatory prose is Russian. Do not translate an
identifier or alter a proper name, email, or URL to claim Russian localization.

Use content that makes sense for the actual requested task and established
product domain. Different rows/cards/items must contain meaningfully different
Russian examples, rather than the same repeated placeholder. Use internally
consistent names, dates, quantities, and amounts where the scenario requires
them. Generated examples are demonstration content, not real user records,
approved product facts, or evidence of an existing screen. Never invent features,
business rules, links to sources, or component behavior to make examples realistic.
If the task/domain is insufficiently established, report that exact content gap.

## Show content variation

For each distinct content-bearing layout used in a scenario, show realistic
short, typical, and long content cases, so the effect on the component and screen
is visible. Apply the same check to explicitly requested component work.

- **Short:** a concise title/value/body and sparse content where supported.
- **Typical:** representative text and content density for the actual scenario.
- **Long:** a plausible long title, value, multiline body, or dense list where
  those inputs are supported. Stay within verified input limits; do not make up
  a limit or use meaningless repeated characters as the long example.

Choose the variation appropriate to the actual property: fixed action labels
must remain meaningful and supported. Different lengths are content examples,
not new component variants or speculative loading/error/empty product states.
Show zero items or absent content only where the requested scenario or inspected
sources establish that behavior; a short-text case alone does not imply an empty
state is supported.

Place the cases in the authorized output where they can be inspected together:
different items in the screen when that exposes the behavior, or clearly labeled
Russian preview frames using linked instances of existing components. For
component work, previews do not create extra masters/variants. For scenario work,
previews do not authorize changing shared components. Return exact output URLs
and identify which case each node demonstrates; do not claim an unseen case passed.

## Check the rendered result

Inspect short, typical, and long cases at each platform/layout width actually
required by the task. Check text wrapping, supported truncation, container
growth, clipping/overlap, alignment of icons/actions, and the layout's actual
scroll behavior. Record the inspected scope and screenshot evidence.

Do not shorten the long example, shrink typography, guess spacing/sizes, detach
instances, or change masters just to hide a layout failure. Use established
component/layout behavior and verified tokens. Report unsupported behavior or
layout defects with exact node/property references; log token deficiencies in
[token gaps](token-gaps.md) and concrete harness bottlenecks in
[harness proposals](harness-proposals.md). Stop dependent work when required
sources cannot support it. Report remaining content/layout gaps without claiming
all lengths, all widths, or all states were verified.
