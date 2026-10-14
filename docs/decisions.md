# Decision provenance

These entries record direct instructions from Evgeny in the Enqo harness setup
conversation. The table below records the 2026-10-09 instructions; later decisions
are dated separately. These entries establish approval provenance, not a second
copy of the operating rules. Implementation is in the linked authoritative homes;
these decisions do not prove a PR was merged, an asset was published, or a workflow
was tested. No external approval permalink was supplied for this conversation.

| Instruction / source | Authoritative home |
| --- | --- |
| Shared Web/Mobile harness; exact source references and missing-evidence reporting | [AGENTS.md](../AGENTS.md) |
| Move instructions from the Enqo.Design draft to EugeneBondarev/Rulla-design | [Code repository provenance](codebases.md) |
| “все, отныне и впредь это агентский центр и оркестратор” | [AGENTS.md entry and orchestration](../AGENTS.md#start-here) |
| Shared foundations plus platform libraries; migration remains in progress | [Figma map](figma.md#file-map-and-migration-state--2026-10-09) |
| Record concrete improvements, their situation/problem/proposal in GitHub | [Harness proposals](harness-proposals.md) |
| Direct human DS-change request; mandatory reuse/token coverage and a separate gap file | [Authorization](../AGENTS.md#design-system-changes-require-a-direct-human-request), [coverage](design-system.md#required-token-coverage), [token gaps](token-gaps.md) |
| Supplied infrastructure template, outer-copy detach, code/library naming and short descriptions | [Component authoring](component-authoring.md) |
| Explicit creation task; publication only by a human | [Creation boundary](../AGENTS.md#design-system-changes-require-a-direct-human-request), [publication boundary](../AGENTS.md#component-publication-is-human-only) |
| Russian mockups with varied realistic text lengths and content density | [Mockup content](mockup-content.md) |
| Compact predictable structure, clear grouping, no duplicate or conflicting rules | [Repository upkeep](../AGENTS.md#maintain-this-repository), [topic map](../README.md#files) |
| Components must be understandable and usable by another agent without the original chat | [Component descriptions and handoff check](component-authoring.md#minimal-description) |

On 2026-10-12, Evgeny required mandatory DS reuse checks and designer notification,
Flutter/Mobile and Vuetify/Web verification, standard solutions before justified
custom work, code-aligned composition, and a small reusable API. The rule's home is
[component authoring](component-authoring.md#reuse-and-platform-implementation-first);
the existing enqo-component skill invokes it.

On 2026-10-12, Evgeny required Mobile scenario screens to use Scaffold and reflect
the actual focused input/cursor, keyboard visibility/type, and meaningful action
key. The rule and inspected controls live in
[screen entry points](scaffolds.md#mobile-focus-and-keyboard-states), invoked by
enqo-flow. This request does not authorize adding missing keyboard APIs to the DS.

On 2026-10-13, Evgeny required Corner Smoothing when setting rounded corners in
component work. The value and verification procedure live in
[component authoring](component-authoring.md#rounded-corners).

On 2026-10-13, after the component-documentation research in this conversation,
Evgeny requested incorporating the practices into shared instructions with
minimal useful text for people and agents and no extra bureaucracy. The format
and checks live in [minimal description](component-authoring.md#minimal-description);
the related bottleneck is [HP-006](harness-proposals.md#hp-006--separate-component-captions-from-reuse-guidance).

On 2026-10-13, Evgeny approved removing the PR barrier for recording findings:
“Да, давай это изменим. Мне кажется, это лишний барьер.” The scoped direct-record
exception and the remaining PR boundary live in
[repository maintenance](../AGENTS.md#maintain-this-repository).

On 2026-10-13, Evgeny designated the shared Figma arrow legend for every scenario:
preserve its colors, use the appropriate platform/event type, and label a connection
only when otherwise unclear. The exact sources and workflow live in
[scenario connections](scaffolds.md#scenario-connections), invoked by enqo-flow.
Evgeny's follow-up that day specified the arrow-label gap and rounded-bend
radius/smoothing; the same section owns those values and checks.
This request does not authorize changes to the Figma legend.

On 2026-10-13, Evgeny required scenarios to be assembled inside native Figma
Sections with fixed outer margins and a white background whose opacity belongs
to the fill rather than the section. Values and verification live in
[scenario sections](scaffolds.md#scenario-sections), invoked by enqo-flow.

The human-only publication instruction supersedes earlier wording permitting
agent publication with authorization. The original GitLab draft remains separate;
it is not a competing source of current rules. No universal cross-platform scaffold,
screen-versus-sheet rule, component replacement, or global token authority has
been approved here.

For a future adopted decision, add its date, approver, concise instruction/source,
approval link when available (otherwise identify the actual source), and home.
Update the rule in that home instead of copying it into this log. Pending proposals
belong in harness-proposals.md or the relevant gap; do not call them adopted.

On 2026-10-14, after discussing a single skill directory, Evgeny asked for a clear
first-file route for Claude. [CLAUDE.md](../CLAUDE.md) retains the shared import and
explains direct file reading; [AGENTS.md](../AGENTS.md#start-here) owns the task
router. Shared bodies stay in `.agents/skills/`; the textual Claude adapters are
removed. This instruction change does not establish a passed Claude session trial.

On 2026-10-14, Evgeny requested click/tap arrows to originate at the actual trigger
element and replaced external arrow labels with integrated labels. The current
sources, text formatting and endpoint checks live in
[scenario connections](scaffolds.md#scenario-connections). This supersedes the
earlier external-label placement instruction; the bend requirement is unchanged.

On 2026-10-14, Evgeny required agents to inspect final Figma screenshots, repair
visible defects and avoid leaving broken output. The shared procedure lives in
[visual completion](../AGENTS.md#visual-completion). He also authorized immediate
merging of this update and the preceding arrow rules.

On 2026-10-14, Evgeny requested screens without extra presentation wrappers,
meaningful screen names in Layers and a heading/description above each screen to
explain the flow's actions and outcomes. Exact styles, bindings and layout checks
live in [screens and captions](scaffolds.md#screens-and-captions). He authorized
immediate merge of this update and any other remaining PRs.

On 2026-10-14, Evgeny refined arrow routing: labels outside screens, parallel
segments clear of screen edges, entry from the side nearest the actual target,
and minimal arrows, labels and avoidable crossings. The values and checks live in
[scenario connections](scaffolds.md#scenario-connections); screen explanations
remain in their existing caption rule rather than being duplicated on arrows.

On 2026-10-14, after trying the caption layout, Evgeny requested two equal-width
text layers without a caption frame and a different gap. The latest structure,
positioning and checks in [screens and captions](scaffolds.md#screens-and-captions)
supersede the earlier caption-only Auto Layout and spacing instruction.

On 2026-10-14, Evgeny clarified that the caption gap had been misread. The corrected
value lives in [screens and captions](scaffolds.md#screens-and-captions); the two
standalone text layers and equal widths remain unchanged.

On 2026-10-14, Evgeny required horizontal/vertical arrow paths with rounded turns
and consistent gaps between sequential screens. Routing and bend checks live in
[scenario connections](scaffolds.md#scenario-connections); layout measurements
live in [scenario sections](scaffolds.md#scenario-sections).
