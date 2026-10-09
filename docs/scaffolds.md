# Screen entry points

Inspected 2026-10-09. This register distinguishes verified identities from missing
usage decisions. No asset here is declared the universal Enqo scaffold.

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
in `🟣 DS Components • Mobile`. Inspected 2026-10-09. Publication statuses refer
to tool-readable source nodes; see the desktop sync warning in [figma.md](figma.md).

### Scaffold/Default

- Exact source name: `Scaffold/Default`; type: `COMPONENT`.
- Source: [22495:10472](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=22495-10472).
- Component key: `eede9f3c90ffff86d9cb0ce30401b39f6e6e13de`.
- Publication status: `CURRENT`.
- Slot properties: `AppBar#19802:0`, `Body#19802:1`,
  `bottomNavigationBar#19802:2`, `overlay_slot#19971:2`.
- Boolean properties, all default `false`: `Show OverlayLayer#19971:0`,
  `Show FAB#20000:1`, `Show In App Notification#20128:1`.
- Linked existing usage: instance `Scaffold/Default`,
  [271:20615](https://www.figma.com/design/jwDivkSTIiXrDEUtFfmsyE?node-id=271-20615),
  resolved to this component key in the scenario-reference file.

The source description specifies a status bar followed by a context navbar in
AppBar, with the status bar retained when there is no navbar. The exact child
component sources and configuration required by a task must still be inspected;
slot preferred keys alone do not establish those nodes' names or approved usage.
This register identifies the source, not a universal starting composition.

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
