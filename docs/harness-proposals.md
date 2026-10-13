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
   and update its impact rather than creating a duplicate. After fetching the
   current branch, choose the next unused `HP-NNN` ID; do not overwrite another
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
| HP-006 | [Separate component captions from reuse guidance](#hp-006--separate-component-captions-from-reuse-guidance) | approved | 2026-10-13 |
| HP-007 | [Resolve Scaffold status-bar ownership](#hp-007--resolve-scaffold-status-bar-ownership) | proposed | 2026-10-13 |

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
merging the documentation PR. HP-005 is reserved in the separate open
[icon-binding proposal](https://github.com/EugeneBondarev/Rulla-design/pull/2).

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
