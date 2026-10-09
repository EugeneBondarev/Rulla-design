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

## Mobile: two observed scaffold identities

| Exact instance name | Usage evidence | Resolved main component name | Component key |
| --- | --- | --- | --- |
| Scaffold | [269:20978](https://www.figma.com/design/jwDivkSTIiXrDEUtFfmsyE?node-id=269-20978) | Property 1=Default | `90887814f025cb3e9dd07db582a493ba3c9dacc7` |
| Scaffold/Default | [271:20615](https://www.figma.com/design/jwDivkSTIiXrDEUtFfmsyE?node-id=271-20615) | Scaffold/Default | `eede9f3c90ffff86d9cb0ce30401b39f6e6e13de` |

Both resolve to remote components. Published library search returned
`Scaffold/Default`, key `eede9f3c90ffff86d9cb0ce30401b39f6e6e13de`, in
`🟣 DS Components • Mobile`. The source-file URL, source-node URL, complete slot
contract, and canonical/replacement relationship between these two keys remain
unverified. The returned local IDs of remote masters are not source-file URLs.

The published description mentions an AppBar slot containing a status bar and a
context navbar. Their exact source nodes have not been verified; that description
is a discovery lead, not a complete executable recipe.

Needed addition before selecting this as a reusable starting point: open the
source component, record its exact source URL, properties, slots, publication
status, and a linked approved usage or explicit owner selection. Do not guess
which scaffold replaces the other or invent its child components.

## Mobile: bottom-sheet evidence

Inside the observed `Scaffold` instance, an instance named `Modal Bottom Sheet`
resolves to a remote main component named `Property 1=Full Screen`, key
`9aab8beffd99301f8a0f420a646ed528423b6948`. Inspect it through the linked
[Scaffold usage](https://www.figma.com/design/jwDivkSTIiXrDEUtFfmsyE?node-id=269-20978).
Its source-file/node URL and current publication status are unresolved.

Published search also returned a different set named `Bottom Sheet`, key
`87deb71bcb2d522019ff81b0d91ec44374c9746e`, in `🟣 DS Components • Mobile`.
This does not prove that it is the same asset or a replacement.

[Mobile routing sources](codebases.md#mobile) distinguish modal presentation from
content and phone from tablet behavior. For a requested scenario, inspect its
route and linked Figma example before choosing a screen or sheet. Missing source
identity, variant mapping, or contradictory behavior blocks that choice; propose
the exact missing row here. Do not create a substitute component.
