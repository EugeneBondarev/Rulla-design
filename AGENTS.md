# Rulla-design agent instructions

## Start here

[Rulla-design](https://github.com/EugeneBondarev/Rulla-design) is the shared agent
center and orchestration entry point for Enqo Web and Mobile design work. It holds
the common instructions, skills, source references, and approved decisions.
Existing source asset and skill names are preserved. For a screen, sheet, or
multi-screen scenario, use
[enqo-flow](.agents/skills/enqo-flow/SKILL.md). Read
[Figma references](docs/figma.md), [scaffold references](docs/scaffolds.md), and
[design-system evidence](docs/design-system.md) before editing Figma. Read the
relevant implementation through [codebases](docs/codebases.md).

For an explicit component creation/change request, use
[enqo-component](.agents/skills/enqo-component/SKILL.md). For an audit, use
[enqo-ds-audit](.agents/skills/enqo-ds-audit/SKILL.md).

Read the current [Figma file map and migration rules](docs/figma.md) before
choosing library sources. Platform separation is in progress; do not treat the
historical combined file as already foundations-only or its components as obsolete.

## Orchestrate a task

Start each task by reading this file and the relevant shared skill. When executing
inside another repository, explicitly load these instructions while respecting
that repository's own instructions. Do not assume a GitHub link injects context.

1. Identify the requested outcome, platform, target Figma nodes or code checkout,
   and the operations authorized by the task.
2. Select the skill linked above and resolve its exact Figma/code sources through
   the docs. Check access to the required tools before dependent work.
3. Order the work by actual dependencies: source discovery, the requested edits,
   then structural, visual, or implementation checks appropriate to those edits.
   Report unresolved prerequisites using the procedure below.
4. Return evidence and proposed documentation corrections to this repository.
   Keep shared workflows and approved decisions here; link to the actual Figma
   assets and implementation repositories instead of duplicating their contents.

## No invented sources or standards

1. Never invent an existing component, screen, template, token, variant, property,
   URL, node ID, component key, repository path, mapping, or approval. Never
   present an inference or proposal as an observed fact or an adopted rule.
2. Before directing anyone to use a Figma asset, give its exact case-sensitive
   name and node URL. For component reuse, also resolve its source component or
   set, key, requested properties/variant, and publication status. An instance
   URL is usage evidence; it is not a verified source-component URL.
3. For variables/styles, record the exact name, collection/mode where applicable,
   ID/key, and a linked node with the actual binding. Do not rename tokens into
   plausible semantic names. Do not claim a raw value is a token.
4. For implementation claims, cite the real repository, file, symbol, and inspected
   commit. Similar names or appearance do not prove a Figma/code mapping.
5. Resolve sources with available tools first. Reopen references needed for this
   task; a previous inspection is dated evidence, not a live guarantee. Never
   ask the user to inventory something the tools can inspect.
6. If required evidence is missing, inaccessible, stale, or conflicting, stop the
   dependent action. Report what is missing, where you looked, what it blocks,
   and the exact documentation addition or decision needed. Continue independent
   work. Ask a targeted question only when discovery cannot resolve the gap.
7. No fallback to generic UI patterns, guessed values, or another component
   because it looks close. Explicitly authorized new designs may have new output
   names and product copy; label these as new output, never as existing standards.
   Return their actual URLs after creation.

## Design-system changes require a direct human request

Never change the design system unless a human directly requests that specific
design-system change. This covers creating, editing, renaming, moving, deleting,
or publishing shared components/sets/variants and their property definitions;
variables, collections, modes, aliases, and values; typography/paint/effect styles;
foundations; and design-system token files or code. Limit edits to the expressly
requested assets and properties. A component-change request does not authorize
creating tokens or changing other shared assets unless those changes are included.

Building a scenario, finding a defect, recording a proposal or token gap, and
requests to improve the resulting screen do not authorize design-system changes.
Report the needed change with exact references and the requested scope. Existing
explicit authorization is sufficient for that scope; do not ask for it again.

## Scenario boundary

An ordinary scenario request means composition from existing, verified assets:
no new DS components, variants, tokens, or styles; no detached instances; no
changes to shared masters. It does not implicitly invoke component creation.
New screen frames, layout containers, text, and instance overrides are allowed
within the task, using verified source layout, styles, bindings, and properties.
If those sources cannot support the task, report the gap instead of manufacturing
a replacement. Supported instance overrides affect only the authorized output;
they must not change a master or bypass its supported API. Do not draw lookalike
components or create local components/styles/tokens to evade this boundary.
A direct human DS change request can expand only its stated scope.

Choose Web and Mobile sources independently. Do not equate a web surface with a
mobile modal route or a Flutter class with a Figma component by name. Explain
screen versus sheet selection using an exact existing screen/route or an approved
decision; otherwise identify the missing decision.

## Required component and token coverage

Use verified existing components for UI elements and the verified scaffold,
slots, and layout rules for composition. An arbitrary frame is not a substitute
for a missing component. Layout containers and task-specific text are permitted
as described above, with their visual properties covered by the design system.

Every applicable visual property must use existing verified design-system tokens:
colors (fills, strokes, text, icons, surfaces), typography (font family, weight,
size, line height, letter spacing), spacing (padding and gaps), sizes (including
applicable minimum/maximum, icon, and control dimensions), corner radii, and
effects. Resolve the actual source, exact identity, selected mode, and binding
using [design-system evidence](docs/design-system.md). Preserve verified bindings
inherited from source components rather than overriding their internals.
Hug/Fill and other layout behaviors are not numeric token values; verify them
against the chosen source layout instead of inventing a token for them.

A style reference alone does not prove token coverage: verify its token mapping.
A raw value inherited from a master also does not prove coverage. If a suitable
token, mapping, or supported binding is missing or cannot be verified, report the
affected property and record it in [docs/token-gaps.md](docs/token-gaps.md).
Do not invent a token/name, guess a value, hardcode a temporary replacement,
select a token solely because its value matches, or repair the source asset
without a direct human request. Stop the dependent edit and continue independent
work. Report a binding limitation accurately; never claim an unsupported binding
exists. Never claim full coverage while required gaps remain unresolved.

## Evidence and completion

Describe facts as observed, conclusions as inferred, changes in policy as
proposed, and unresolved items as unknown. Existence/publication does not establish
canonical status. Figma describes design; code describes that revision's
implementation; neither proves what is deployed.

Return source links and output links, what changed, structural/visual checks,
and remaining gaps, including linked token-gap entries. Check actual instance keys,
property values, variable/style bindings, and screenshots. Do not claim all states,
responsiveness, accessibility,
production parity, persistence, or cross-agent behavior were tested without evidence.

Audits leave inspected assets and rules unchanged unless fixes are explicitly
requested. The standing authorization to record proposals and token gaps still
applies; an explicit instruction prohibiting all writes takes precedence. Publishing libraries,
deleting shared assets, merging branches, and production changes require explicit
authorization for that action. Do not store credentials here.

## Improve the harness

During every task, consider whether an observed bottleneck makes the system harder
for agents to use. This includes Figma organization, components, foundations,
code mappings, instructions, skills, tool access, orchestration, and verification.
Do not invent an improvement just to produce an entry.

When a concrete problem is found, record or update a proposal in
[docs/harness-proposals.md](docs/harness-proposals.md). Follow that file's process:
describe the situation, exact evidence, problem and affected task, proposed change,
and observable acceptance check. Search existing proposals and add evidence to an
existing item instead of creating duplicates. Capture the proposal when discovered;
do not silently fix shared assets or expand the task to implement it.

Record token-specific deficiencies in [docs/token-gaps.md](docs/token-gaps.md).
For a related systemic harness improvement, link that entry from the proposal
instead of duplicating its evidence or treating the proposal as a token definition.

The user's standing instruction authorizes recording evidence-backed proposals
and token gaps through a branch/PR without asking again for each entry. If write access is
unavailable or the user explicitly prohibits all writes, return the exact proposed
entry and report that it was not saved.
Never claim a proposal was recorded in GitHub from an unsent draft.

New proposals start as `proposed`. Adoption and implementation require explicit
human authorization; a proposal is not a standard or permission to change assets.
Record approved decisions in [decisions](docs/decisions.md), and keep each adopted
rule in its main document. Authorized documentation edits after initial setup go
through a branch/PR. Never promote chat speculation, memory, or generated summaries
into standards. In the task report, link recorded proposals and any unresolved
documentation changes; do not claim automatic synchronization.
