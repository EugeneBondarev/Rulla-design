# Screen entry points and scenario connections

Sources inspected 2026-10-09; Mobile scaffold/keyboard/search-field evidence below
was refreshed 2026-10-12. Observed identities and unresolved decisions are distinct.
No single scaffold is shared universally across Web and Mobile.

## Web: App Shell

- Exact source name: `App Shell`; type: `COMPONENT`.
- Source: [24227:2308](https://www.figma.com/design/nOYabg1FJaeMH7iUe2QRdi?node-id=24227-2308), page `App Shell` (`24227:24`).
- Component key: `60b72f754d7f240bc6ef5cae9c9cdd5a5c70ebb4`.
- Publication status returned by Figma: `CURRENT`.
- Size at inspection: 1440 × 960; this is an observed size, not a breakpoint rule.
- Component property: `Slot#24227:1`, type `SLOT`; child `Slot`, node `24227:2309`.
- Related implementation entry: [Web App.vue](codebases.md#web). This is an
  architecture reference, not a verified one-to-one component mapping.

Before composition, inspect the slot's current content, instance behavior, and the
target route's layout. The observed slot alone does not specify which navigation,
content surface, or screen belongs inside it. Use the exact existing route/screen
for that choice; if none resolves it, propose that missing composition rule here.

## Web: Sheet

- Exact source name: `Sheet`; type: `COMPONENT`.
- Source: [24227:16](https://www.figma.com/design/nOYabg1FJaeMH7iUe2QRdi?node-id=24227-16), page `Sheet` (`24227:21`).
- Component key: `dc85b0bb444da7489de3bfbcaf9bd5de9236a15f`.
- Published search result places this key in `🟣 DS Components • Web`.
- Publication status of the source node: `CHANGED`. The edited source and
  published asset must not be silently treated as the same revision.
- Size at inspection: 500 × 500. Property `Slot#24227:0`, type `SLOT`;
  child `Slot`, node `24227:13`.
- Actual bindings are recorded in [design-system](design-system.md).

Its name and slot do not establish modal behavior, a bottom-sheet presentation,
or its place inside `App Shell`. Resolve published versus edited source and an
actual usage example before using it for a scenario. Do not publish it to resolve
this uncertainty.

## Mobile: verified platform sources

Both sources are on page `Scafold` (exact spelling),
[22495:10441](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=22495-10441),
in `🟣 DS Components • Mobile`. Original inspection: 2026-10-09; Scaffold was
refreshed 2026-10-12. Publication statuses refer to tool-readable source nodes;
see the desktop sync warning in [figma.md](figma.md).

### Scaffold/Default

- Exact source name: `Scaffold/Default`; type: `COMPONENT`.
- Source: [22495:10472](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=22495-10472).
- Component key: `eede9f3c90ffff86d9cb0ce30401b39f6e6e13de`.
- Publication status: `CURRENT` on 2026-10-09; `CHANGED` on 2026-10-12.
- Slot properties: `AppBar#19802:0`, `Body#19802:1`,
  `bottomNavigationBar#19802:2`, `overlay_slot#19971:2`.
- Boolean properties, all default `false`: `Show OverlayLayer#19971:0`,
  `Show FAB#20000:1`, `Show In App Notification#20128:1`;
  `Show Keyboard#23073:0` verified on 2026-10-12, also default `false`.
- Linked existing usage: instance `Scaffold/Default`,
  [271:20615](https://www.figma.com/design/jwDivkSTIiXrDEUtFfmsyE?node-id=271-20615),
  resolved to this component key in the scenario-reference file.

The source description specifies a status bar followed by a context navbar in
AppBar, with the status bar retained when there is no navbar. The exact child
component sources and configuration required by a task must still be inspected;
slot preferred keys alone do not establish those nodes' names or approved usage.
Use this source for new Mobile screens under the keyboard rule below; the actual
AppBar/Body composition remains task-specific. This does not authorize migration
of existing screens or library edits.

### Bottom Sheet

- Exact source name: `Bottom Sheet`; type: `COMPONENT_SET`.
- Source: [22495:10484](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=22495-10484).
- Component-set key: `87deb71bcb2d522019ff81b0d91ec44374c9746e`.
- Publication status: `CURRENT`.
- Variant property: `Property 1`; options `Partial`, `Full Screen`;
  default `Partial`.
- Slot property: `Slot#19989:5`.

[Mobile routing sources](codebases.md#mobile) distinguish modal presentation from
content and phone from tablet behavior. Inspect the requested route and the exact
Figma usage before choosing these variants. Names do not establish an automatic
mapping to ModalBottomSheetPage or another Flutter class.

## Mobile: focus and keyboard states

For new Mobile scenario output, assemble each screen/state inside a linked
`Scaffold/Default` from the source above. Identify which scenario states expect
software-keyboard input and which field is focused. A field appearing on screen
alone does not mean the keyboard should be open.

1. In every state expecting keyboard input, select the actual field's supported
   focus state and show its cursor, with one identifiable active input. Use exact
   field sources/properties, not renamed arbitrary frames. Enable the scaffold's
   `Show Keyboard#23073:0` and preserve its linked keyboard. Do not show a keyboard
   with no focused field, or omit it from a state that requires it.
2. Select the keyboard for the actual input: text, number/code, phone, email,
   multiline, or another verified type. Inspect the field/route through
   [codebases](codebases.md#mobile) and the matching Flutter
   [keyboardType API](https://api.flutter.dev/flutter/material/TextField/keyboardType.html).
   Resolve the exact existing Figma source/variant and target iOS/Android layout;
   neither the default nor a similar name establishes that mapping.
3. Choose the action by what actually happens on press: search executes a query,
   next moves to the next real input, done finishes entry, send sends content,
   or newline inserts a line break when supported. Verify the actual callback or
   focus transition and Flutter
   [textInputAction API](https://api.flutter.dev/flutter/material/TextField/textInputAction.html).
   A label/icon alone does not implement an action; do not leave generic return
   accidentally when the scenario needs a different action.
4. Configure through verified instance properties or an established source swap;
   record values, source keys, and consuming nodes. Respect
   [platform action support](https://api.flutter.dev/flutter/flutter_test/TextInputAction.html):
   do not assume identical labels, icons, blue color, position, or action support
   on iOS and Android. If a layout has no action key, show the verified keyboard
   and the scenario's actual way to finish input; do not draw a nonexistent key.
   Apply [Russian content](mockup-content.md) to labels/keyboard locale, preserving
   technical names. Unsupported/unverified mappings block that dependent choice;
   they do not authorize DS edits.
5. Verify keyboard-open layout: focused field/cursor visible, correct input and
   action configuration, accessible content/CTA, overlap, safe area, and actual
   resize/scroll behavior. Check applicable next-field/dismissal transitions and
   keyboard-hidden states that occur in the scenario. Return exact state, field,
   scaffold, keyboard and action-node URLs plus screenshots and untested behavior.
   Do not invent extra product states for a checklist.

### Verified controls — 2026-10-12

All sources below are in `🟣 DS Components • Mobile`. This is bounded evidence,
not a global keyboard inventory or a verified Flutter-to-Figma mapping.

| Role | Exact source and identity | Observed API/state |
| --- | --- | --- |
| Keyboard in scaffold | [Keyboard, 23073:13497](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=23073-13497) | INSTANCE; hidden by default; `Type=Default`, `Show suggestions#6238:0=false`, `Show accessory bar#6238:6=false` |
| Keyboard source | [Keyboard, 22398:5664](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=22398-5664); key `62b1d904cc961f9335222ce70f9ddb6038aa9027` | COMPONENT_SET, `CURRENT`; `Type`: `Default`, `Numbers and Punctuation`, `Emoji`, `Find`, `Find and Replace`, `Web Form`, `Web`. Source defaults for suggestions/accessory are `true`, unlike the scaffold instance. |
| Default layout source | [Type=Default, 22398:5774](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=22398-5774); key `d3df6b0b5e41744c48fd75d4f028253f07bd7adb` | Nested `Keys`, 22398:5779, uses `_Keyboard - iPhone Layouts` with `Type=Letters - Lowercase`. Inspected default shows Latin letters. |
| Return key source | [Mode=Light, Type=Return-Prominent, 22398:5040](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=22398-5040); key `773d3b36443ab3f7a0747cba6e9ec287eb5c7491` | Used by nested instance `Return`; rendered as a blue glyph key. Parent `_Keys - iPhone`, [22398:5006](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=22398-5006), key `c90a32ded84bde54d46f18802f7e3ff3c4ed7b95`. No dedicated semantic action property found in this inspected API. |
| Search field source | [Search Text Field, 22559:1201](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=22559-1201); key `8b88b0fe2ab4cdb9ad242c81ad70bb9cd0f762fe` | `Property 1`: `Default`, `Tap`, `fill_focus`, `long`, `Fill`; visible `Cursor` instances found in [Tap, 22559:1211](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=22559-1211) and [fill_focus, 22559:1213](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=22559-1213). Inspect the actual field rather than infer focus from a name. |

`Numbers and Punctuation` is not a verified phone, OTP, or number-pad mapping.
The inspected source page did not establish an Android keyboard or Russian-letter
layout. Search/Next/Done/Send configuration remains unresolved; do not fake it by
editing an unrelated key property. See
[HP-004](harness-proposals.md#hp-004--resolve-mobile-keyboard-configuration).

## Mobile: unresolved older usage

In the scenario-reference file, instance `Scaffold`,
[269:20978](https://www.figma.com/design/jwDivkSTIiXrDEUtFfmsyE?node-id=269-20978),
resolved to a different remote main component named `Property 1=Default`, key
`90887814f025cb3e9dd07db582a493ba3c9dacc7`. Its source-file/node URL and relationship
to the current `Scaffold/Default` remain unresolved.

Inside that instance, `Modal Bottom Sheet` resolved to a remote main component
named `Property 1=Full Screen`, key `9aab8beffd99301f8a0f420a646ed528423b6948`.
Its source URL and relationship to the current `Bottom Sheet` set remain unresolved.
Neither old usage is automatically deprecated or replaced by this discovery.

The source URLs for the current platform components are now verified; the
remaining question is the migration relationship between old and current keys.
See [HP-001](harness-proposals.md#hp-001--record-component-replacements-during-migration).
Do not detach, recreate, delete, or migrate these instances to resolve the gap
without an authorized change and verified usage impact.

## Scenario sections

Assemble every requested Web or Mobile scenario inside a native Figma `SECTION`
at the authorized destination. Include the whole flow: screens/states, their
captions, arrows and necessary labels. Measure their combined outer bounds and
position/resize the section to leave **400 px on each side**: left, right, top, and bottom.
Recalculate these margins after changing the flow. Set section position and size
from the bounds; do not invent Auto Layout padding properties for a Section.

In a sequence of screens, keep **250 px between adjacent screen roots**, measured
edge to edge along the sequence direction: right edge to left edge in a row, or
bottom edge to top edge in a column. Measure screen bounds, not caption bounds or
screen centers. Recalculate after resizing/rearranging screens; this is a canvas
layout value, not a product-UI spacing token.

The section background is **white with fill opacity 70%**. In the Plugin API,
use a SOLID fill with `color: {r: 1, g: 1, b: 1}` and paint `opacity: 0.7`.
Keep the section's own `opacity` at `1` (100%); the flow content must not become
translucent with it. These are user-specified canvas-presentation values, not
product UI tokens or new design-system assets.

Read back the SECTION type, fill/color/paint opacity and node opacity; measure
all four margins against the final flow bounds and the gaps between sequential
screens; inspect the result. Return
the actual section/output links and checked margins with the scenario evidence.

### Screens and captions

Keep each screen's existing root scaffold/instance directly in the Section.
**Do not add a presentation frame around each screen or around a screen plus its
caption.** Preserve the screen's own root and internal layout containers; this
rule does not remove frames needed by its actual UI. Name that output root in
Layers with a meaningful Russian screen/state title, matching its visible heading;
do not rename the shared source component or leave generic names such as `Frame 1`.

Above every screen, place **two standalone TEXT nodes directly in the Section**,
with equal widths and aligned left edges. Do not wrap them in a frame, Auto Layout
or group; no caption container/name should appear above the screen:

- **Heading:** the screen/state title; `Heading/M`, **23 px**, `Text/Primary`.
- **Description:** 1–2 short Russian sentences explaining what happens here:
  the relevant user action, its result or the next step; `Body/S`, **14 px**,
  `Text/Secondary`. Use only behavior established by the task and inspected flow.

Keep **4 px vertically between the bottom of the Heading text box and the top
of the Description text box**. After text changes, remeasure heights and reposition
the Description to retain that gap. This is a human-specified canvas-positioning
value within the caption, not an arrow-label gap or a new spacing token.
Use the actual text styles and color bindings; do not reproduce them with raw
values. Preserve the style's line height (28 px / 20 px at inspection): 23 / 14 px
are font sizes, not fixed text-box heights. Let descriptions wrap/grow without
clipping and keep them visibly associated with their screen, outside its product UI.
Do not invent a new fixed caption-to-screen gap.

Sources inspected read-only on 2026-10-14 in
[`• Typography`, 328:64152](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=328-64152)
of `🟣 Design System`:

| Role | Exact asset identity | Source / observed values |
| --- | --- | --- |
| Heading style | `Heading/M`; style ID `S:1eec501a91c1839e86ce3f6fec3ef7ba0284df1e,`; key `1eec501a91c1839e86ce3f6fec3ef7ba0284df1e` | [Роли, 19157:76156](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=19157-76156); font-size binding `Font/Size/23`, ID `VariableID:19050:44842`, key `308eea238842a1adeebf9edeaf64456812ecf90c`; Typography Web/Mobile both 23 |
| Description style | `Body/S`; style ID `S:29dfcda6ed86475b1d655095a936d3b2c93df1cf,`; key `29dfcda6ed86475b1d655095a936d3b2c93df1cf` | [Body/S binding, 19157:76157](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=19157-76157); font-size binding `Font/Size/14`, ID `VariableID:19050:44840`, key `aae06dc5a17ca8947b4ab553a9098e173b6440f3`; Typography Web/Mobile both 14 |
| Heading color | `Text/Primary`; ID `VariableID:6398:328840`; key `b7a5e3d3d3dc9a518e501eca2b4dc6774668d368` | Bound on [Роли, 19157:76156](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=19157-76156); Color • Variables, Light/Dark |
| Description color | `Text/Secondary`; ID `VariableID:6418:328925`; key `1dc4ec8b32c1284387cdd9d1073df22f7b45e4ed` | Binding evidence: [Name, 18884:188](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=18884-188); Color • Variables, Light/Dark |

Reopen these assets and resolve local/imported IDs and effective modes before use.
Read back output names, direct Section parents, equal text widths, the measured
gap, text-style identities, color bindings, actual sizes and wrapping.
Include captions in the Section's final flow bounds and the
[visual completion check](../AGENTS.md#visual-completion); return their node links.

## Scenario connections

For every Web or Mobile scenario, use the user-designated arrows to show actual
connections between the displayed screens/states. Current integrated-label source:
section [`Стрелки`, 22186:18630](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=22186-18630)
on page [`Infra`, 20597:159663](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=20597-159663)
in `🟣 Design System`, inspected read-only on 2026-10-14. The earlier
[`Стрелки`, 22172:18563](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=22172-18563)
still contains four standalone vectors; it is historical appearance evidence,
not the source for the current integrated-label workflow.

| Exact adjacent legend label | Current `Connector line` source | Earlier vector source | Enqo scenario usage |
| --- | --- | --- | --- |
| Tap | [22186:18591](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=22186-18591), purple, solid | [Arrow 2, 22172:18564](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=22172-18564) | Web and Mobile: explicit click/tap action |
| Gesture | [22190:21282](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=22190-21282), turquoise, solid | [Arrow 5, 22172:18565](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=22172-18565) | Mobile: an actual supported gesture |
| Haptic Feedback | [22190:21287](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=22190-21287), blue, dotted | [Arrow 3, 22172:18566](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=22172-18566) | Mobile: evidenced tactile feedback |
| Automatically | [22190:21292](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=22190-21292), pink, dotted | [Arrow 6, 22172:18567](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=22172-18567) | Web and Mobile: an automatic transition |

These are native **CONNECTOR** nodes with built-in `connector.text`, not component
assets. Reopen and clone the exact source; preserve stroke paint, thickness,
dash pattern and endpoint caps. Sources have a 1 px stroke, `CIRCLE_FILLED` start
and `ARROW_EQUILATERAL` end. Configure the copy's actual endpoints, not the legend's.

1. **Event:** Web uses Tap and Automatically; Mobile may use all four for evidenced
   events. Haptic Feedback describes tactile feedback, not an extra screen.
   Use the fewest arrows needed to understand the requested flow, preserving
   meaningful branches and outcomes. Do not invent actions, conditions, timings
   or transitions; a state without a transition needs no arrow.
2. **Origin:** A click/tap arrow starts at the actual triggering button/hit target
   in the output screen, not the screen edge, shared master or a decorative layer.
   Use `connectorStart.endpointNodeId` for that element where supported and place
   the start on its boundary. A gesture starts at its interaction surface; an
   automatic transition refers to its initiating state/event, without a fake button.
   If the trigger or attachment is unresolved, report it instead of substituting
   the screen as origin.
3. **Label:** Add short Russian text only when necessary to understand the transition.
   Put screen context, action and outcome in the [screen Description](#screens-and-captions)
   when that explains them clearly; use an arrow label for transition-specific
   information better explained there. Do not repeat the same explanation in both.
   The integrated label must sit **entirely outside every screen**, never over its UI.
   Route the connector so its built-in text lands on an outside segment; do not
   add a separate text node or detach the label to work around its placement.
   Use `connector.text.characters`. Set `connector.text.fontSize = 12` and text fill
   to the arrow's actual
   stroke color/opacity, not the adjacent legend label. Load the existing font
   before editing. Read back the result: sources have empty labels, mostly 16 px,
   with black fill; their defaults do not satisfy this rule automatically.
4. **Routing:** Straight path segments go **only left, right, up or down**, never
   diagonally, including exits and entries inside screens. Use axis-aligned
   routing (`ELBOWED` for turns); a `STRAIGHT` connector is allowed only when
   horizontal or vertical. Round turns under the Bends rule below; rounded turn
   arcs are allowed, diagonal shortcuts or arbitrary curved paths are not.
   Between screens, route along their outside edges. Any exterior segment
   parallel to a screen must stay **at least 16 px from its boundary**, measured
   from the visible stroke edge. Only the short exit from the trigger and entry
   to the destination may run inside a screen; do not route along or across its UI.
   Enter the destination from the side giving the shortest clear path to the actual
   target element. Do not enter at the top and cross the whole screen for a target
   near the bottom. For a screen-level destination, use the nearest clear edge
   without inventing a target control. Minimize arrow crossings and overlaps where
   possible, keeping branches and direction readable when a crossing is unavoidable.
5. **Bends:** The earlier **16 px radius / 60% smoothing** rule remains. Current
   sources report radius 24 px; the available CONNECTOR API exposes radius as
   read-only and no smoothing field. Report the mismatch under
   [HP-009](harness-proposals.md#hp-009--resolve-native-connector-bend-controls)
   and resolve it before claiming the bend passed. Do not use VECTOR setters or
   redraw a connector as a vector to bypass its integrated text. Apply rounding
   to path turns, not a surrounding frame; annotation values are not UI tokens.

Keep destination/direction clear and route arrows without obscuring content.
Inspect saved endpoints, event/style, label size/color and placement outside screens,
horizontal/vertical straight segments, parallel-segment clearance, entry side,
crossings and rounded bends; apply
[visual completion](../AGENTS.md#visual-completion). Return source, trigger and
output links. Drawn arrows do not establish prototype reactions, application
behavior or dynamic attachment by appearance alone.
