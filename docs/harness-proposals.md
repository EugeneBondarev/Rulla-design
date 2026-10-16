# Harness improvement proposals

This is the shared record for concrete improvements discovered by any agent
working on the Enqo harness. It covers Figma files/assets, foundations, code
mappings, instructions, skills, access, orchestration, and verification.
Recording/implementation permissions are defined in
[AGENTS.md](../AGENTS.md#maintain-this-repository). This file owns the proposal
format, lifecycle, and evidence entries.

Token-specific deficiencies are recorded in [token-gaps.md](token-gaps.md).
Link the relevant `TG-NNN` entry here when proposing a systemic improvement;
do not duplicate its finding or treat a proposal as permission to change the DS.

## Record a proposal

1. Read existing entries. If the same bottleneck is recorded, add new evidence
   and update its impact rather than creating a duplicate. After refreshing
   `main`, choose the next unused `HP-NNN` ID; do not overwrite another
   agent's additions. Resolve simultaneous changes before pushing.
2. Record the date and actual task/situation; the observed problem and its impact;
   exact Figma names/node URLs/keys, code paths/commits, or other source links;
   the smallest proposed change; an observable acceptance check; and the decision
   or access needed. Distinguish observed facts, inferences, and unknowns.
3. Start with status `proposed`. Use `approved`, `deferred`, `rejected`, or
   `implemented` only with linked evidence of that decision or completed work.
   Approval is distinct from implementation. Do not invent an owner or approver.
4. Save and report under [repository maintenance](../AGENTS.md#maintain-this-repository).
   After authorized implementation, link actual output/checks, record approval
   provenance in [decisions](decisions.md), and update the rule's authoritative home.
   Keep the proposal history and outcome; do not turn a proposal into an
   undocumented standard.

Use ordinary prose under the fields below. Do not pad entries with guessed
priority, confidence, savings, severity, or speculative benefits. If no concrete
bottleneck was found, no proposal is required.

## Index

| ID | Proposal | Status | Date |
| --- | --- | --- | --- |
| HP-001 | [Record component replacements during migration](#hp-001--record-component-replacements-during-migration) | proposed | 2026-10-09 |
| HP-002 | [Add an entry link from Figma to the agent center](#hp-002--add-an-entry-link-from-figma-to-the-agent-center) | proposed | 2026-10-09 |
| HP-003 | [Require rule loading before Figma writes](#hp-003--require-rule-loading-before-figma-writes) | proposed | 2026-10-09 |
| HP-004 | [Resolve Mobile keyboard configuration](#hp-004--resolve-mobile-keyboard-configuration) | proposed | 2026-10-12 |
| HP-005 | [Verify icon colors after button state changes](#hp-005--verify-icon-colors-after-button-state-changes) | proposed | 2026-10-13 |
| HP-006 | [Separate component captions from reuse guidance](#hp-006--separate-component-captions-from-reuse-guidance) | approved | 2026-10-13 |
| HP-007 | [Resolve Scaffold status-bar ownership](#hp-007--resolve-scaffold-status-bar-ownership) | proposed | 2026-10-13 |
| HP-008 | [Resolve reusable AppBar centerTitle support](#hp-008--resolve-reusable-appbar-centertitle-support) | proposed | 2026-10-14 |
| HP-009 | [Resolve native connector bend controls](#hp-009--resolve-native-connector-bend-controls) | proposed | 2026-10-14 |
| HP-010 | [Resolve shared Button property-read errors](#hp-010--resolve-shared-button-property-read-errors) | proposed | 2026-10-15 |
| HP-011 | [Pilot a machine-readable scenario contract](#hp-011--pilot-a-machine-readable-scenario-contract) | proposed | 2026-10-16 |

## HP-009 — Resolve native connector bend controls

**Status:** proposed. **Date:** 2026-10-14.

**Situation and evidence:** While updating arrow-origin and integrated-label rules,
read-only inspection found native CONNECTOR sources in
[`Стрелки`, 22186:18630](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=22186-18630).
For example, [Tap / Connector line, 22186:18591](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=22186-18591)
is ELBOWED with radius 24 px and a built-in text sublayer. The available Plugin API
types expose ConnectorNode.cornerRadius as read-only and no cornerSmoothing field.
No setter was attempted and no Figma nodes were edited.

**Problem and impact:** The existing [bend rule](scaffolds.md#scenario-connections)
requires values the current connector API does not expose for writing. The latest
human request changes origins/labels, not that earlier bend requirement. A flow
cannot be claimed fully compliant by preserving the observed default.

**Proposed change:** Verify whether an available Figma UI/tool can configure the
required bend values on native connectors. If unsupported, ask for a specific
bend-rule decision while retaining the integrated label and exact arrow sources.

**Acceptance / needed decision:** A saved native connector demonstrates the adopted
bend behavior with inspectable evidence, or a human approves the precise rule
revision after the limitation is verified. No vector substitution, shared-source
edit, publication or new rule is authorized by recording this proposal.

## HP-001 — Record component replacements during migration

**Status:** proposed. **Date:** 2026-10-09.

**Situation and evidence:** The [file map](figma.md) records migration from the
historical combined file into platform libraries. The Mobile source
[`Scaffold/Default`, 22495:10472](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=22495-10472)
has key `eede9f3c90ffff86d9cb0ce30401b39f6e6e13de`. Existing scenario instance
[`Scaffold`, 269:20978](https://www.figma.com/design/jwDivkSTIiXrDEUtFfmsyE?node-id=269-20978)
resolves to a different main-component key,
`90887814f025cb3e9dd07db582a493ba3c9dacc7`. The [scaffold register](scaffolds.md)
records both observations and the unresolved relationship.

**Problem and impact:** An agent cannot determine whether the current platform
source replaces the older usage, coexists for a different purpose, or needs
migration work. Guessing could select an incorrect source or break instance links.

**Proposed change:** Start with these scaffold keys: locate the older source,
record both exact node URLs, inspect affected usage, and obtain the intended
relationship. Add a compact old-source/new-source/status/usage/decision record
to the relevant register. Extend it only for actual migrated assets needed by
tasks; do not infer mappings from names or build an unverified global inventory.

**Acceptance:** For a scenario using these keys, an agent can select its source
and explain whether migration is required using linked facts and an explicit
decision. Existing instances retain their links unless an authorized migration
changes them.

**Needed decision:** The intended relationship between the keys and the scope of
any migration. No replacement or deprecation has been approved by this proposal.

## HP-002 — Add an entry link from Figma to the agent center

**Status:** proposed. **Date:** 2026-10-09.

**Situation and evidence:** The user designated
[Rulla-design](https://github.com/EugeneBondarev/Rulla-design) as the agent center
and asked how agents entering from Figma would find its rules. Existing source
cover pages are [`/cover`, 343:66776](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=343-66776),
Web [`Cover`, 22220:3](https://www.figma.com/design/nOYabg1FJaeMH7iUe2QRdi?node-id=22220-3),
and Mobile [`Cover`, 22220:3](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=22220-3).
Page identities were inspected; their cover content has not been audited for an
existing equivalent notice in this task.

**Problem and impact:** Entering through a component or screen URL does not by
itself establish that an agent has loaded the repository instructions.

**Proposed change:** Inspect the covers for an existing entry notice. Add or
update a small linked notice pointing to
[AGENTS.md](https://github.com/EugeneBondarev/Rulla-design/blob/main/AGENTS.md)
and the file map. If a dedicated page is useful, create a new `Agent start here`
page and record its actual URL after creation. Keep detailed rules in GitHub.
The notice must state that required instructions and task-specific sources must
be read before edits, and missing access/evidence must be reported.

**Acceptance:** Each source file has one discoverable entry notice with working
links. An entry from a component URL can resolve the rules through the configured
agent workflow. The notice is not presented as a technical enforcement mechanism.

**Needed authorization:** The specific Figma notice/page edits. None were made
while recording this proposal.

## HP-003 — Require rule loading before Figma writes

**Status:** proposed. **Date:** 2026-10-09.

**Situation and evidence:** This repository contains
[AGENTS.md](../AGENTS.md), client imports, and shared skills. The
[README](../README.md#client-entry-points) describes client discovery and its
limitations. This setup has not implemented a controlled rule loader or a Figma
write gate. The user requires agents to use the repository before Figma work.

**Problem and impact:** A repository link, cover notice, or written instruction
alone does not technically prevent a client from calling Figma write tools
without loading the required context.

**Proposed change:** First identify the actual client and execution path used for
the initial scenario. Configure loading of AGENTS.md, the selected skill, and
required documents from an explicit revision. If technical enforcement is needed,
implement a controlled tool path that permits writes only after those fetches
succeed, records the revision and loaded files, and rejects missing dependencies.
Identify and close direct write paths that would bypass that check before calling
the enforcement complete. Do not claim the loader verifies semantic understanding.

**Acceptance:** A fresh-session scenario loads the required files before its first
write. An unavailable repository or required document prevents that write and
produces a precise blocker. Logs show the source revision. The claim is limited
to the clients/tool paths actually configured and tested.

**Needed decision:** Which client/execution path to configure first and whether
client instructions alone or a controlled writer is required for that scope.
No loader, hook, gateway, or new tool permission is installed by this proposal.

## HP-004 — Resolve Mobile keyboard configuration

**Status:** proposed. **Date:** 2026-10-12.

**Situation and evidence:** The user requires focused Mobile inputs with matching
keyboard type and action. [Inspected controls](scaffolds.md#verified-controls--2026-10-12)
identify `Scaffold/Default`'s `Show Keyboard#23073:0`, its nested `Keyboard`, and
the actual source/API. The default is an iPhone letter layout with a blue `Return`
glyph. Its `Type` options and `_Keys - iPhone` API do not expose a dedicated
Search/Next/Done/Send semantic action selector in this inspected scope. Numeric,
phone/OTP, Android, and Russian-letter mappings were not established. This is
bounded evidence, not a global claim that such assets are absent.

Optional accessory inspection also hit `Component set for node has existing errors`
when reading instances of [`_Button - Symbol`, 22398:5488](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=22398-5488).
Those property reads remain unverified; they do not invalidate the separately
verified scaffold visibility control. No source repair was attempted.

**Problem and impact:** An agent can enable the keyboard, but cannot yet resolve
every required input/OS/action/locale configuration from these recorded sources.
Guessing variants or altering a generic glyph would claim unsupported behavior.

**Proposed change:** Inspect other existing assets and actual Mobile field code;
record exact matching sources/configurations where they exist. For a remaining
gap, propose the smallest source/property or documentation change tied to a
concrete scenario. DS edits need a direct human request; publication is human-only.
Do not generate all theoretical combinations or add a library to fill the record.

**Acceptance:** An agent can configure and explain a concrete focused input,
keyboard type/locale, and action/control using verified sources/properties/code.
The output matches the platform behavior or reports the specific unresolved gap.

**Needed decision:** Verified per-task mappings and explicit authorization for
any DS repair discovery shows is necessary. No keyboard asset was changed here.

## HP-006 — Separate component captions from reuse guidance

**Status:** approved for the documentation change by Evgeny's 2026-10-13 request
in this conversation; [decision provenance](decisions.md). **Date:** 2026-10-13.

**Situation and evidence:** The user showed a `FormattingOptionsSection` caption
listing button counts and pixel measurements. At inspected main commit
`1071a6dc6d16ad429d1666d40d96192a113b3401`,
[component-authoring.md](https://github.com/EugeneBondarev/Rulla-design/blob/1071a6dc6d16ad429d1666d40d96192a113b3401/docs/component-authoring.md#minimal-description)
grouped visible text and reuse details. It did not require measurement captions;
the inference is that the grouping encouraged excessive text.

**Problem and impact:** Captions can repeat inspectable geometry rather than help
people and agents choose and use components.

**Proposed change:** Clarify the existing [description format](component-authoring.md#minimal-description)
and its skill check; no separate per-component documents.

**Acceptance:** In the next authorized component task, inspect the caption,
native Description/links, and preview labels against the real API. They explain
use, important choices, and known limits without incidental measurement lists.
No fresh-session behavioral trial is claimed by this documentation change.

**Needed decision:** The instruction change is authorized; existing Figma
descriptions require their own explicit edit scope. Adoption in main depends on
merging the documentation PR. HP-005 is recorded below; its originating
[icon-binding PR](https://github.com/EugeneBondarev/Rulla-design/pull/2) preserves the change history.

## HP-005 — Verify icon colors after button state changes

**Status:** proposed. **Date:** 2026-10-13.

**Situation and evidence:** The existing [FormattingOptions Row, 23160:1384](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=23160-1384)
contains AppButton instances whose icon vector fills have direct Icon/Secondary
overrides. Cloning these buttons and changing Type to Primary or State to Disabled
initially retained the gray icon fill. The inspected Primary source
[22774:5347](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=22774-5347)
instead has a white token-bound icon. The Disabled source has the separate
[TG-001](token-gaps.md#tg-001--appbutton-disabled-icon-binding) binding gap.

**Problem and impact:** Correct variant/property values do not prove the correct
rendered icon color. Copied overrides can silently survive state changes.

**Proposed change:** Add a scoped check of the visible icon paint and binding
after icon swaps and state/type changes; preserve intended overrides and remove
stale ones only within the authorized output. Shared-source repair requires its
own direct authorization.

**Acceptance:** A fresh linked instance can show Default, selected Primary, and
Disabled with the inspected colors/bindings; any inherited raw source fill is
reported rather than described as token coverage.

**Needed decision:** Adoption of this shared workflow check and explicit scope
for any AppButton source repair. The new
[FormattingOptionsSection](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=23191-1386)
already had stale overrides removed locally; selected colors were read back,
Disabled preview bindings were applied locally, and shared masters were preserved.


**Additional evidence, 2026-10-15:** In
[VoiceInputSection](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=23423-12122),
switching the linked AppButtons from Secondary to Tonal kept the public
`Icon#22774:6` values for close (`22495:9383`) and stop (`23396:22352`), but both
visible glyphs became `more_horizontal` (`22495:9373`). The inspected
[Tonal / S / Default / Icon only source, 22782:1266](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=22782-1266)
has empty componentPropertyReferences on its nested Icon. This is a component
property mapping gap in addition to the paint-override issue above. The scoped
VoiceInputSection fix swaps the nested linked icon instances to the intended
sources and binds their vector fills to existing Icon/Primary. Shared AppButton
masters remain unchanged. Final rendered buttons show close and stop correctly.

**Proposed check extension:** Verify the rendered icon source as well as its
paint after changing Type/State; a correct public Icon property alone is not
acceptance evidence. Shared AppButton mapping repair still requires explicit
scope. No shared-rule adoption is claimed by recording this evidence.

**Additional Web evidence — 2026-10-15:** In the refreshed
[Voice Input scenario](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=21944-32721),
swapping the filled-state Send instance to the verified Primary/Default source
[22007:138708](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=22007-138708)
retained the earlier disabled icon paint. The source uses \`Icon/On primary color\`
(\`VariableID:6505:398555\`); the swapped instance retained
\`VariableID:6975:163151\`. The two authorized scenario instances, including
[Text ready](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=22268-4242),
now use the existing source paint. Masters were unchanged. This extends HP-005's
state-change verification evidence to Web; it authorizes no shared Button repair.

## HP-007 — Resolve Scaffold status-bar ownership

**Status:** proposed. **Date:** 2026-10-13.

**Situation and evidence:** Read-only inspection of
[Scaffold/Default, 22495:10472](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=22495-10472),
key `eede9f3c90ffff86d9cb0ce30401b39f6e6e13de`, returned CHANGED.
The source has a direct linked
[Status Bar, 22495:10474](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=22495-10474)
before its separate
[AppBar slot, 22495:10473](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=22495-10473).
However, its native description instructs putting Status Bar and a context navbar
inside AppBar and keeping Status Bar there even when no navbar exists.
[The earlier description-based record](scaffolds.md#scaffolddefault) quotes that
guidance; it is not a current proof of correct containment.

**Problem and impact:** Following the description literally can duplicate the
device status bar or reserve its height twice. Slot names alone also do not prove
exact mapping for each screen: the inspected
[chat Scaffold](https://git.aimadev.space/platform/Enqo.Mobile/-/blob/d12f3e6819ce70f892bbb2c7df4ee16955b694c6/common/lib/features/chat/presentation/screens/chat_data.dart)
places buildAppBar() inside body, MessageInputArea in bottomNavigationBar, and
uses extendBody=true. Its layout therefore needs screen-specific mapping rather
than an assumption that every top bar occupies Scaffold.appBar.

**Proposed change:** Resolve which level owns Status Bar, document one consistent
composition, and repair the authorized source description/structure accordingly.
The observed separate system layer is a fitting candidate; this proposal does
not adopt it as a new standard or authorize source edits.

**Acceptance:** A linked screen with a context app bar, a screen without it, and
an applicable keyboard-open state each contain one device status bar, with safe
areas counted once. Per-screen slot mapping and any body overlap are explicit.

**Needed decision:** The intended Status Bar ownership and direct authorization
for the precise Figma description/structure change. No Figma nodes, token
definitions, Flutter code, or library publication were changed in this audit.

## HP-008 — Resolve reusable AppBar centerTitle support

**Status:** proposed. **Date:** 2026-10-14. Related Scaffold finding: [HP-007](#hp-007--resolve-scaffold-status-bar-ownership).

**Situation and evidence:** The user requested a Chat Info bar in Examples.
[GroupChatInfoScreen](https://git.aimadev.space/platform/Enqo.Mobile/-/blob/d12f3e6819ce70f892bbb2c7df4ee16955b694c6/common/lib/features/user_info/presentation/screen/group_chat_info_screen.dart)
uses SliverAppBar with centerTitle=true, a two-line title, AppBackButton, and
GroupChannelDetailsMenu. The inspected Figma
[AppBar source](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=23046-1005),
key `898a36982101519ca69372908acece2f75b66673`, exposes slots and visibility
controls but no centerTitle property.

**Problem and impact:** Centering the title in the remaining space alone does
not guarantee alignment to the full bar when leading/actions widths differ.
A single configured example does not establish general centerTitle behavior.

**Proposed change:** Inspect actual centered usages and resolve a small supported
API/layout solution for global centering, including asymmetric actions and long
titles. Any shared-master/property change requires a direct human request.

**Acceptance:** A linked instance centers a fitting title against the whole bar
with one leading action and varying trailing content, and reproduces the
documented long-title collision behavior. Sliver expansion is separate scope.

**Current scoped result:** The authorized
[Chat Info example](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=23321-1330)
remains linked to AppBar. Its two side slots are balanced and its two title lines
are centered. Two additional authorized Examples show
[back only](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=23336-1348)
and [back plus search and menu](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=23336-1387).
Both title lines match the full bar center at widths 393 and 320, including after
reopening the saved instance. Local title-content insets compensate for the
different side widths; these examples do not add a shared centerTitle property
or promise automatic compensation after replacing the action composition.
Native slot positioning/size overrides were rejected or did not persist through
the API, so the final examples use supported content overrides and retain their
AppBar link. AppBar, AppTile, AppButton masters and publication were unchanged.
The separate typography finding is
[TG-002](token-gaps.md#tg-002--labelm-font-size-role-binding).

## HP-010 — Resolve shared Button property-read errors

**Status:** proposed. **Date:** 2026-10-15.

**Situation and evidence:** Documentation-only work on
[Messaging Input](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=3280-128473)
and [QuillInput](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=22012-2392)
encountered `Component set for node has existing errors` when reading
componentProperties on existing nested toolbar buttons. For example, Bold
instance `I22010:144190;22012:2178` resolves to
[Button variant 1500:106417](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=1500-106417),
key `4e1062cdbafdd567f868e3bbdab4a3d23a5abf19`, in
[Button, 6979:212369](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=6979-212369),
set key `a1b7ebbf565a8e7d7e7aaa3bf24f47a05975d4d3`.
The error existed before presentation edits and remained afterward. Source keys,
geometry, content, bindings, and readable properties matched before/after checks.
The underlying cause has not been established.

**Problem and impact:** An agent can inspect the toolbar and source links but
cannot verify or safely rely on every nested button property through this API.
Screenshots do not prove the property API is healthy. This is separate from the
Mobile accessory observation in HP-004.

**Proposed change:** Inspect this exact Button source in the editor and API,
identify the invalid configuration or tool incompatibility, and propose the
smallest evidenced repair. Preserve variant keys and instance overrides;
do not rebuild or detach the buttons as a workaround.

**Acceptance / needed decision:** The cited Bold instance and affected toolbar
buttons return their properties without the error, with source links and visual
states preserved. Shared Button repair needs a direct human request;
publication remains human-only. This record authorizes no source repair.

## HP-011 — Pilot a machine-readable scenario contract

**Status:** proposed. **Date:** 2026-10-16.

**Situation and evidence:** The user requested research into a machine-readable
companion to the visual flow for Flutter implementation agents. Read-only
inspection of [Поиск чатов и сообщений, 6064:86304](https://www.figma.com/design/V1EKgtI2h6sOnE5MW9ZvoH?node-id=6064-86304)
found 14 screen instances and 19 native connectors. Captions specify partial
search failures, preserving results during pagination, retrying only the failed
request/page, and highlighting an opened message for 1.5 seconds. These are
observed design statements, not evidence of approval or implemented behavior.
For example, [Описание · 11 · Чаты доступны, сообщения — ошибка, 6064:86981](https://www.figma.com/design/V1EKgtI2h6sOnE5MW9ZvoH?node-id=6064-86981)
says retry requests only messages. Connector [6064:86307](https://www.figma.com/design/V1EKgtI2h6sOnE5MW9ZvoH?node-id=6064-86307)
has the exact name `Flow · Tap · Повторить поиск сообщений · 23242:8499 → 23100:21105`,
but both endpointNodeId values reference the enclosing section with coordinates.
The corresponding current screen instances are [6064:86873](https://www.figma.com/design/V1EKgtI2h6sOnE5MW9ZvoH?node-id=6064-86873)
and [6064:86470](https://www.figma.com/design/V1EKgtI2h6sOnE5MW9ZvoH?node-id=6064-86470);
names embedded in arrows are not reliable current endpoint mappings.

**Problem and impact:** A rendered map or raw node dump cannot alone establish
events, conditions, independent request states, retry scope, or API semantics.
Treating every illustrated state as a route or inferring links from obsolete IDs
can produce an incorrect implementation. Request timing, stale-response handling,
and back-navigation state preservation are not resolved by the inspected captions.

**Proposed change:** Pilot one versioned YAML scenario contract in Rulla-design,
with stable semantic IDs, exact Figma node links, inspection/version evidence,
states, events and trigger references, conditions, effects, outcomes, and a few
acceptance cases. Distinguish design evidence, approved intent, implementation
references, proposals, and unknowns. Keep unknown APIs/timing as explicit open
questions; do not invent routes, methods, or values. Separate screen presentation
from request, focus/keyboard, and pagination state; record haptics as effects.
Use one shared schema for structure and a separate small reference/graph check
if the pilot is adopted. JSON Schema alone does not establish behavioral coverage.
The agent should maintain the model and visual map together, cross-checking
semantic bindings rather than reconstructing behavior from arrow geometry.
Store each behavior rule once; generated diagrams/test outlines are derived views.

The existing [AllChannelsSearchController](https://git.aimadev.space/platform/Enqo.Mobile/-/blob/21d282885ab186f61298c66eb3414f62e12f5b9c/common/lib/features/home/presentation/controllers/all_channels_search_controller.dart)
and [router](https://git.aimadev.space/platform/Enqo.Mobile/-/blob/21d282885ab186f61298c66eb3414f62e12f5b9c/common/lib/core/services/router/router.dart)
use Riverpod and go_router. This supports adapting the contract to existing Dart
code without prescribing a new runtime; it does not prove implementation of the
combined chat/message search shown in Figma.

**Research references:** [Tinder's Android payment-flow case study](https://medium.com/tinder/scaling-out-tinder-android-payment-flow-using-state-machine-e14ef0591b6),
[Square Workflow](https://square.github.io/workflow/),
[Koordinates/Stately case study](https://stately.ai/blog/2023-11-28-koordinates-and-stately-case-study),
and [Stately's Figma-state integration](https://stately.ai/docs/figma)
support modeling states/events/effects and linking visuals. They do not establish
an industry-standard Figma-to-Flutter contract. The YAML format above is a proposal.

**Acceptance / needed decision:** Agree the minimal format and pilot scope. A
fresh implementation agent can explain the partial-failure retry, pagination
retry, and message-opening behavior from the contract without reading arrows,
trace each statement to evidence, and report unresolved decisions. Validate
references and concrete acceptance cases against the implemented Flutter flow;
a parseable document is not proof of correct code. Figma remains the visual
reference. No flow file, schema, generator, skill rule, Figma edit, or application
code change is implemented by this research entry.

