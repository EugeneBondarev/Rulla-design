# Screen entry points

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
