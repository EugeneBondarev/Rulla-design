# Rulla-design agent instructions

## Start here

[Rulla-design](https://github.com/EugeneBondarev/Rulla-design) is the shared agent
center and orchestration entry point for Enqo Web and Mobile. Read this file and
choose [enqo-flow](.agents/skills/enqo-flow/SKILL.md) for scenarios,
[enqo-component](.agents/skills/enqo-component/SKILL.md) for explicit component work,
or [enqo-ds-audit](.agents/skills/enqo-ds-audit/SKILL.md) for audits.

Read the relevant sources and topic rules before dependent work:
[Figma file map](docs/figma.md), [screen entry points](docs/scaffolds.md),
[token coverage and evidence](docs/design-system.md), [code references](docs/codebases.md),
[component authoring](docs/component-authoring.md), and
[Russian mockup content](docs/mockup-content.md). The
[README file map](README.md#files) assigns each topic one home.

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
design-system change. This covers creating, editing, renaming, moving, or deleting
shared components/sets/variants and their property definitions;
variables, collections, modes, aliases, and values; typography/paint/effect styles;
foundations; and design-system token files or code. Limit edits to the expressly
requested assets and properties. A component-change request does not authorize
creating tokens or changing other shared assets unless those changes are included.

Building a scenario, finding a defect, recording a proposal or token gap, and
requests to improve the resulting screen do not authorize design-system changes.
Report the needed change with exact references and the requested scope. Existing
explicit authorization is sufficient for that scope; do not ask for it again.

Create a component only when its creation is directly specified in the human's
task. This includes new local or shared masters, component sets, variant
components, and duplicated masters. A request to change an existing component
does not authorize additional components unless their creation is specified.
Scenario composition may create linked instances of existing components; those
instances are not permission to create new masters.

For an explicitly requested new component, follow
[component authoring](docs/component-authoring.md). Its only detach exception
is the new outer `DS Container Template` presentation copy. The header and nested
UI instances remain linked; this exception never applies to scenario composition.

## Component publication is human-only

Agents must never publish components, component sets, or their updates to a Figma
library. Only a human may publish them. This is an absolute agent prohibition,
including when a component task asks for publication. Do not invoke publication
through a tool, API, UI, script, automation, or another agent. Prepare the requested
local work and checks, then return exact asset links and observed status for the
human to publish. Inspecting publication status or importing an existing published
component for reuse is allowed; neither is a publication action.

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

## Design-system coverage

UI composition uses verified existing components, scaffolds, slots, and layout
rules; an arbitrary frame is not a replacement for a missing component. Applicable
visual properties must use existing verified tokens under
[design-system.md](docs/design-system.md#required-token-coverage). Resolve gaps
before dependent edits and record them in [token-gaps.md](docs/token-gaps.md).

## Evidence and completion

Describe facts as observed, conclusions as inferred, changes in policy as
proposed, and unresolved items as unknown. Existence/publication does not establish
canonical status. Figma describes design; code describes that revision's
implementation; neither proves what is deployed.

Return source links and output links, what changed, structural/visual checks,
and remaining gaps, including linked token-gap entries. Check actual instance keys,
property values, variable/style bindings, and screenshots. Do not claim all states,
responsiveness, accessibility, production parity, persistence, or cross-agent
behavior were tested without evidence.

Audits leave inspected assets and rules unchanged unless fixes are explicitly
requested. The standing authorization to record proposals and token gaps still
applies; an explicit instruction prohibiting all writes takes precedence. Component
publication follows the boundary above. Deleting shared assets, merging branches,
and production changes require explicit authorization. Do not store credentials here.

## Maintain this repository

Keep one authoritative home for each rule, using the [README map](README.md#files).
Edit the existing topic/section first; other files link to it instead of restating
it. Skills contain task steps and required links, client adapters only load shared
instructions, and decisions record approval provenance rather than copies of rules.
Before saving, check affected references and remove stale or conflicting wording.
If the human's intent is unresolved, stop the dependent change and report the
conflict rather than inventing precedence.

Do not create a file, folder, skill, register, or process for each new chat request.
Add one only for a distinct recurring need that does not fit an existing home;
state its scope and entry link, and avoid empty scaffolding or speculative fields.
Do not merge unrelated topics just to reduce file count, or delete evidence,
source links, and unresolved findings to make the repository look smaller.

During each task, record concrete bottlenecks in
[harness-proposals.md](docs/harness-proposals.md) and token deficiencies in
[token-gaps.md](docs/token-gaps.md), following their respective entry formats.
Update an existing finding instead of duplicating it; link related entries.
Do not invent findings or silently implement a recorded proposal.

The user's standing instruction authorizes recording these findings through a
branch/PR without asking for every entry. If access is unavailable or all writes
are explicitly prohibited, return the exact entry as unsaved. Never claim an
unsent draft is recorded in GitHub or an open PR is already in the default branch.
Adoption and implementation need the relevant human authorization; keep approval
provenance in [decisions.md](docs/decisions.md). Authorized documentation changes
use a branch/PR.

Never promote chat speculation, memory, or generated summaries into standards.
In the task report, link recorded proposals and any unresolved
documentation changes; do not claim automatic synchronization.
