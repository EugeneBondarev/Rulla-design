# Approved decisions

The user explicitly requested the following operating rules on 2026-10-09 in the
Enqo harness setup task: Web and Mobile share instructions; simple scenarios reuse
existing assets; asset references must be exact; missing evidence must be reported
and a concrete documentation update proposed. Their implementation is
[AGENTS.md](../AGENTS.md). This attribution records the source request; it is not
a claim that the resulting change has already been reviewed or merged.

The user subsequently requested moving the same instruction set into
[EugeneBondarev/Rulla-design](https://github.com/EugeneBondarev/Rulla-design) on
2026-10-09. This is the instruction repository; existing Figma identities and
GitLab code sources retain their exact verified names and URLs. The original
GitLab draft remains separate and is not an adopted competing source of rules.

On 2026-10-09, Evgeny explicitly designated Rulla-design as the agent center and
orchestrator in this task: “все, отныне и впредь это агентский центр и оркестратор”.
The decision applies to the shared Enqo Web/Mobile agent workflows. Its operating
contract is [Start here and Orchestrate a task](../AGENTS.md): start from the shared
instructions, select a skill, resolve exact sources and access, execute authorized
work in dependency order, verify it, and propose needed updates here. This records
the user's approval of the repository's role; it does not claim additional tools,
permissions, automatic context loading, or an execution service were installed.

On 2026-10-09, Evgeny specified the target Figma organization: shared foundations
in `🟣 Design System`, Web components in `🟣 DS Components • Web`, and Mobile
components in `🟣 DS Components • Mobile`. He confirmed that migration is still
in progress and the historical combined file retains components from both
platforms. The exact source links and transitional rules are maintained in
[figma.md](figma.md), with current inspection evidence. The two platform files
are designated agent-first; this is their intended operating model, not proof
that every component already meets that model.

In the same request, Evgeny authorized all agents to record concrete harness
improvement proposals in one GitHub file, describing the situation, problem, and
proposed change. The process and entries live in
[harness-proposals.md](harness-proposals.md). Recording a proposal is authorized;
adoption, asset changes, publication, and merging remain separate actions.

On 2026-10-09, Evgeny directly required that agents never change the design system
without a human request for that specific DS change. Scenario composition must
use existing components and tokens for applicable colors, typography, spacing,
sizes, and other visual properties. Agents must report token deficiencies and
record where they occur in a separate file. The operating rules are in
[AGENTS.md](../AGENTS.md); the evidence register is [token-gaps.md](token-gaps.md).
Recording a gap does not authorize its repair. This records the user's decision,
not proof that existing Figma assets already have complete token coverage.

On 2026-10-09, Evgeny required new components to be placed in a copy of the exact
infrastructure template he linked. Only the new outer copy is detached; its
`Slot` holds the actual component and its header remains linked with the component
name. Names must come from project code or the platform library (Flutter/Mobile,
Vuetify/Web); descriptions must briefly explain usage and key supported states.
The inspected sources and workflow are maintained in
[component-authoring.md](component-authoring.md). This authorizes that presentation
procedure during directly requested component creation, not a component-creation
task now, source-template edits, or migration of existing components.

On 2026-10-09, Evgeny explicitly prohibited component creation unless creation is
directly specified in the task, and prohibited all agent publication of components:
only a human may publish them. This supersedes earlier wording allowing agent
publication with explicit authorization. The prohibition includes updates and
delegated/automated publication. The governing rules live in
[AGENTS.md](../AGENTS.md); component workflows return local checked assets for a
human to publish.

No universal scaffold, screen-versus-sheet selection rule, component replacement,
or global token authority has been approved in this file.

For a future adopted decision, record the exact decision, platform/scope,
approver, approval date, linked approval (MR/issue or other accessible record),
linked Figma/code evidence, and canonical destination document. Keep pending
proposals beside the relevant gap or in the MR; do not list them as adopted.
