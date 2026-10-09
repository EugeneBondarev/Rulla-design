# Rulla-design

[Rulla-design](https://github.com/EugeneBondarev/Rulla-design) is the shared agent
center and orchestration entry point for Enqo Web and Mobile. Start each task with
[AGENTS.md](AGENTS.md): it routes work to the relevant skill, exact Figma/code
sources, required checks, and documentation updates. Shared rules, workflows, and
approved decisions are maintained here.

Existing Figma asset names, Enqo code-repository names, and enqo-* skill IDs are
preserved: moving the instructions does not rename or migrate those sources.

## Files

This is the topic map. Each rule has one authoritative home; read linked topic
rules rather than using this map as a second instruction set.

| Group | Home | Contents |
| --- | --- | --- |
| Entry | [AGENTS.md](AGENTS.md) | Task routing, evidence standards, authorization, publication boundary, repository upkeep |
| Figma sources | [docs/figma.md](docs/figma.md) | File roles, migration, library/page inventory, access |
| Screen entry | [docs/scaffolds.md](docs/scaffolds.md) | Scaffold/sheet identities, APIs, usage and selection gaps |
| Design system | [docs/design-system.md](docs/design-system.md) | Token coverage requirements and inspected bindings/JSON provenance |
| Components | [docs/component-authoring.md](docs/component-authoring.md) | Infrastructure template, naming, placement and descriptions |
| Mockup content | [docs/mockup-content.md](docs/mockup-content.md) | Russian content, realistic variation and layout checks |
| Code sources | [docs/codebases.md](docs/codebases.md) | Repository/path/commit references and inspected architecture |
| Findings | [docs/token-gaps.md](docs/token-gaps.md), [docs/harness-proposals.md](docs/harness-proposals.md) | Token deficiencies and broader harness proposals, respectively |
| Provenance | [docs/decisions.md](docs/decisions.md), [docs/starter-review.md](docs/starter-review.md) | Human decision sources and historical starter review; not competing rulebooks |
| Workflows | [.agents/skills/](.agents/skills/) | The three task workflows selected by AGENTS.md |
| Client loading | [CLAUDE.md](CLAUDE.md), [GEMINI.md](GEMINI.md), [.claude/skills/](.claude/skills/) | Imports/adapters; no independent design rules |
| Data | [tokens/typography.json](tokens/typography.json) | Existing token data; inspected provenance is in design-system.md |

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
