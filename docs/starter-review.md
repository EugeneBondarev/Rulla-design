# Starter review — 2026-10-09

Reviewed all 13 Markdown files in the supplied `enqo-agent-starter.zip` and
replaced the starter's generic directions with the entry points in this repository.
This is a review of the starter and the inspected sources, not a complete audit
of every Enqo Figma file or component.

| Starter statement or omission | Correction | Evidence / destination |
| --- | --- | --- |
| “Search before creating” can allow a scenario to grow the DS. | Scenario requests are reuse-only; missing assets produce a gap report. | [AGENTS.md](../AGENTS.md), user's explicit requirement. |
| Asset links required only “when accessible” / “when possible”. | Exact identities are prerequisites for dependent actions; access failures stay explicit. | [AGENTS.md](../AGENTS.md). |
| “Reuse existing screen templates” without a source. | Register actual source components; the inspected Templates page is empty. | [Figma references](figma.md), [scaffolds](scaffolds.md). |
| No distinction between scaffold, web surface, and bottom sheet. | Record different keys and properties; require a route/screen basis for selection. | [scaffolds](scaffolds.md), [codebases](codebases.md). |
| One unspecified design-system library URL. | Link verified nodes individually; state missing source-library URLs and mappings. | [figma](figma.md), [scaffolds](scaffolds.md). |
| Placeholder repository URLs, paths, and maintainers. | Actual repository URLs and 18 existing paths at pinned commits; ownership remains unknown. | [codebases](codebases.md). |
| Hypothetical semantic roles and generic token advice. | Actual Sheet variable names, keys, collections, modes, and consuming-node link. No assumed token pipeline. | [design-system](design-system.md). |
| No published-versus-edited source distinction. | Sheet is CHANGED; App Shell is CURRENT at inspection. | [scaffolds](scaffolds.md). |
| enqo-flow described only multi-screen work. | Covers one screen, one sheet, or multiple screens, Web and Mobile. | [enqo-flow](../.agents/skills/enqo-flow/SKILL.md). |
| enqo-component triggers on almost any mention of states/tokens. | Restricted to explicit DS component work. | [enqo-component](../.agents/skills/enqo-component/SKILL.md). |
| Audit prohibition only mentions published libraries / production. | Audit is read-only across all assets until fixes are requested. | [enqo-ds-audit](../.agents/skills/enqo-ds-audit/SKILL.md). |
| Skill paths assume the current directory is this repository. | Relative links resolve from each skill's location. | All three skills. |
| Claude import depends on version and surrounding files. | Add an explicit CLAUDE.md import; keep small skill adapters with matching descriptions. | [CLAUDE.md](../CLAUDE.md), .claude/skills/. |
| “Knowledge Promotion Candidate” asks for confidence/urgency without improving the rule. | Report the missing fact, blocked action, destination file, exact proposed text, evidence, and decision needed. | [AGENTS.md](../AGENTS.md). |
| Asking the agent what it loaded is the suggested test. | Require evidence-producing read-only trials and then a real composition trial. | [README](../README.md). |

No fabricated component names, canonical replacements, screen/sheet rules, source
URLs, or token mappings were added to fill the remaining gaps. No Figma design,
shared library, application code, or existing typography JSON was changed by
this documentation setup.

## Repository move

The user requested this same structure in Rulla-design on 2026-10-09. Its GitHub
repository was inspected and empty. The prior Enqo.Design draft at commit
`a6c4b5fcdd572420322a1e03deb17b7a9c75f798` supplied the instruction files. Repository
entry points and contribution wording now target GitHub; Figma IDs, component
names, code sources, and evidence limitations were preserved. The typography
JSON was copied unchanged. This move does not publish or modify Figma assets.
