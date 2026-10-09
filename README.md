# Rulla-design

[Rulla-design](https://github.com/EugeneBondarev/Rulla-design) is the shared agent
center and orchestration entry point for Enqo Web and Mobile. Start each task with
[AGENTS.md](AGENTS.md): it routes work to the relevant skill, exact Figma/code
sources, required checks, and documentation updates. Shared rules, workflows, and
approved decisions are maintained here.

Existing Figma asset names, Enqo code-repository names, and enqo-* skill IDs are
preserved: moving the instructions does not rename or migrate those sources.

## Files

```text
AGENTS.md
CLAUDE.md
GEMINI.md
docs/
  figma.md
  scaffolds.md
  design-system.md
  component-authoring.md
  mockup-content.md
  codebases.md
  decisions.md
  harness-proposals.md
  token-gaps.md
  starter-review.md
.agents/skills/
  enqo-flow/SKILL.md
  enqo-component/SKILL.md
  enqo-ds-audit/SKILL.md
.claude/skills/
  enqo-flow/SKILL.md
  enqo-component/SKILL.md
  enqo-ds-audit/SKILL.md
tokens/typography.json
```

[Starter review](docs/starter-review.md) lists the inaccurate or insufficient
instructions removed. [Scaffolds](docs/scaffolds.md) identifies the verified
entry nodes and the evidence still missing. Existing typography data is preserved.

[Figma file map](docs/figma.md) records the current shared/Web/Mobile split and
the rules for working during migration. Every agent records concrete bottlenecks
and improvements in [harness proposals](docs/harness-proposals.md), using exact
evidence and the procedure defined there. Recording an idea does not authorize
implementing it.

[Component authoring](docs/component-authoring.md) defines the exact infrastructure
template, outer-copy detach exception, linked header, code/library naming, and
short descriptions for explicitly requested new components.

Design-system changes require a direct human request for that change. Scenario
work must reuse verified components and cover applicable visual properties with
existing tokens. Agents report missing or unverified coverage in
[token gaps](docs/token-gaps.md), without creating replacements or silently fixing
shared assets. The full authorization and coverage rules are in AGENTS.md.

New components may be created only when directly specified in the task.
Component publication, including updates, is always performed by a human;
agents may prepare and check local work but never publish it.

[Russian mockup content](docs/mockup-content.md) requires Russian UI copy and
descriptions, realistic varied short/typical/long examples, and visible layout
checks. Exact source component, property, and token names remain unchanged.

## Start a task

1. Open Rulla-design as the agent's working directory, on the branch containing
   these instructions. GitHub reported `main` as the default branch; the
   repository was empty when this initial content was prepared on 2026-10-09.
2. Let the agent read AGENTS.md and activate the relevant skill. For one screen,
   sheet, or scenario, use enqo-flow. It must resolve exact Figma sources before
   writing, using the links in docs and current tool evidence.
3. Provide access to the Enqo Figma account and relevant code repositories in that
   client. Connections and credentials are not installed by these files.
4. If a required asset or rule cannot be verified, the agent reports the exact
   missing dependency and proposes a specific documentation update. It must not
   manufacture a plausible substitute.

Agents launched inside a different repository do not automatically inherit these
instructions. Explicitly load this repository's AGENTS.md and required skills,
while preserving the other repository's own instructions and access boundaries.

## Client entry points

| Client | Shared instructions | Skills |
| --- | --- | --- |
| Codex | AGENTS.md | .agents/skills/ |
| Claude Code | CLAUDE.md imports AGENTS.md | .claude/skills/ adapters read .agents/skills/ bodies |
| Gemini CLI | GEMINI.md imports AGENTS.md | .agents/skills/ |

Adapters contain no separate design rules. Their skill descriptions match the
canonical files. Check the active client's version, configuration, and loaded
project context before claiming discovery works. Documentation references:
[Codex instructions](https://learn.chatgpt.com/docs/agent-configuration/agents-md),
[Codex skills](https://learn.chatgpt.com/docs/build-skills),
[Claude memory](https://code.claude.com/docs/en/memory),
[Gemini context](https://geminicli.com/docs/cli/gemini-md/),
[Gemini skills](https://geminicli.com/docs/cli/skills/).

## Acceptance trials

File validation does not prove agent behavior. Run these in fresh Codex, Claude
Code, and Gemini CLI sessions with the required access:

1. Read-only Web entry-point check: inspect App Shell and Sheet from the register.
   Require exact live names, keys, properties, source URLs, publication status,
   and relevant code commit. Reject invented templates or a claimed bottom-sheet
   mapping based only on the word Sheet.
2. Read-only Mobile entry-point check: resolve the two recorded scaffold keys to
   source components. Require source links and evidence for selecting one; if
   unresolved, require an accurate gap report and exact proposed documentation
   addition. No Figma mutation is allowed in this trial.
3. After source gaps are resolved, use one real user-specified simple scenario
   and authorized destination per platform. Require linked editable output,
   verified instance keys/bindings, visual inspection, and no new DS assets or
   detached instances. Record which behavior and states were actually checked.
   Require Russian authored UI content and linked short/typical/long content
   cases with rendered layout checks, preserving exact technical identifiers.
4. In a task with a real token deficiency, require a linked token-gap entry with
   exact target/property/mode and inspected scope, the correct evidence
   classification, and a stopped dependent edit. Reject invented tokens, temporary
   hardcoding, unrequested DS repair, and unsupported full-coverage claims.

No fresh-session cross-client or end-to-end composition trial is claimed by this
initial documentation change. Remaining source gaps are explicit in the docs.
