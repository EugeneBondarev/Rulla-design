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

## Scenario boundary

An ordinary scenario request means composition from existing, verified assets:
no new DS components, variants, tokens, or styles; no detached instances; no
changes to shared masters. It does not implicitly invoke component creation.
New screen frames, layout containers, text, and instance overrides are allowed
within the task, using verified source layout, styles, bindings, and properties.
If those sources cannot support the task, report the gap instead of manufacturing
a replacement. A separate explicit DS change request can expand this scope.

Choose Web and Mobile sources independently. Do not equate a web surface with a
mobile modal route or a Flutter class with a Figma component by name. Explain
screen versus sheet selection using an exact existing screen/route or an approved
decision; otherwise identify the missing decision.

## Evidence and completion

Describe facts as observed, conclusions as inferred, changes in policy as
proposed, and unresolved items as unknown. Existence/publication does not establish
canonical status. Figma describes design; code describes that revision's
implementation; neither proves what is deployed.

Return source links and output links, what changed, structural/visual checks,
and remaining gaps. Check actual instance keys, property values, variable/style
bindings, and screenshots. Do not claim all states, responsiveness, accessibility,
production parity, persistence, or cross-agent behavior were tested without evidence.

Audits are read-only unless fixes are explicitly requested. Publishing libraries,
deleting shared assets, merging branches, and production changes require explicit
authorization for that action. Do not store credentials here.

## Improve these instructions

After relevant work, identify factual drift or a rule missing for reliable
execution. Propose the destination file, exact replacement/addition, supporting
links, and which task it unblocks. State whether it is a factual correction or a
new decision. After initial repository setup, authorized documentation edits go into a branch/PR; a new decision
becomes an adopted standard only after explicit human approval. Record approved
decisions in [decisions](docs/decisions.md); keep the rule in one main location.
Never promote chat speculation, memory, or generated summaries into standards.
