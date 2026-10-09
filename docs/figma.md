# Figma references

## File map and migration state — 2026-10-09

The user confirmed the current migration and intended file responsibilities on
2026-10-09. File keys, pages, selected source components, and library subscriptions
were checked with the Enqo Figma connection. Exact library names are corroborated
by Figma library metadata; the Mobile source URL was read from its open Figma tab.
This is a bounded snapshot, not a complete component inventory.

| Exact file/library name | File key and link | Current state | Intended responsibility |
| --- | --- | --- | --- |
| 🟣 Design System | [ig93klQ0XqzeWI1Rm1fHnc](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc) | Historical combined file. Shared foundations and Web/Mobile components remain here while migration continues. | Shared foundations reused by both platforms; platform components move to their respective files. |
| 🟣 DS Components • Web | [nOYabg1FJaeMH7iUe2QRdi](https://www.figma.com/design/nOYabg1FJaeMH7iUe2QRdi) | Contains part of the Web component system. Migration is incomplete. | Web components, organized for agent use. |
| 🟣 DS Components • Mobile | [8YfQ8OljtPhKsdbCxytn6Y](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y) | Contains part of the Mobile component system. Migration is incomplete. | Mobile components, organized for agent use. |

The Mobile URL supplied in the request repeated the Web file. The verified
Mobile source above replaces that duplicate. `jwDivkSTIiXrDEUtFfmsyE` below is a
separate scenario-reference file; it is not the Mobile component library.

## Rules during migration

1. Begin discovery in the relevant platform file for platform components, and in
   the shared file for foundations. If a needed component is not there, inspect
   its existing usage and source in the historical file before declaring a gap.
2. Do not infer that the historical file is deprecated, foundations-only already,
   or safe to delete. Do not infer that a platform file contains all required
   components. These are target responsibilities, not completed migration facts.
3. Resolve the actual source key and publication state for each reused asset. If
   versions coexist, require a linked replacement/usage decision; similar names
   or appearance do not establish a replacement. Preserve existing dependencies
   until an authorized migration resolves them.
4. The Web and Mobile files are designated agent-first by the user. Record
   self-discovered improvements in [harness-proposals](harness-proposals.md),
   with exact evidence, instead of silently changing shared assets or standards.
   Explicitly requested edits still follow their authorized task scope.
5. Keep this map current after verified moves or file changes. Update a specific
   fact with evidence; do not claim the whole migration is complete from one move.

## Observed shared foundations and remaining components

The shared file contains these local variable collections at inspection:

| Exact collection name | Modes | Variable count |
| --- | --- | --- |
| Color • Variables | Light, Dark | 125 |
| Numbers • Aliases | Web, Mobile | 18 |
| Typography | Web, Mobile | 19 |
| Spacing • Aliases | Web, Mobile | 29 |

These are selected observations, not the complete collection list or an approval
of every value. Related pages include
[`•  Color`, 11169:23528](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=11169-23528),
[`• Spacing`, 7468:409378](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=7468-409378), and
[`• Typography`, 328:64152](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=328-64152).

Components still exist in the shared file. A verified example is the `Button`
component set, key `a1b7ebbf565a8e7d7e7aaa3bf24f47a05975d4d3`,
[6979:212369](https://www.figma.com/design/ig93klQ0XqzeWI1Rm1fHnc?node-id=6979-212369)
on page `• Buttons`. Its existence does not establish a replacement relationship
to the Mobile `AppButton` or any Web button.

Both platform files report no local variable collections in this snapshot. They
subscribe to `🟣 Design System` and their respective platform library. No local
collections does not mean no tokens: inspect remote bindings and actual modes.

The open Mobile desktop file displayed an unsaved-changes/reconnect warning
during this inspection. Desktop-local changes may differ from the tool-readable
source. `CURRENT` statuses below refer to the inspected source nodes; they do not
prove that every local desktop change has synced. Resolve any affected discrepancy
before relying on it. No Figma edits or publication were performed for this update.

## Web

File key: `nOYabg1FJaeMH7iUe2QRdi`.

| Exact name | Node type | Direct reference | Use |
| --- | --- | --- | --- |
| App Shell | COMPONENT | [24227:2308](https://www.figma.com/design/nOYabg1FJaeMH7iUe2QRdi?node-id=24227-2308) | Source identity and slot: see [scaffolds](scaffolds.md). |
| Sheet | COMPONENT | [24227:16](https://www.figma.com/design/nOYabg1FJaeMH7iUe2QRdi?node-id=24227-16) | Has unpublished changes; see [scaffolds](scaffolds.md). |
| Templates | PAGE | [24395:2](https://www.figma.com/design/nOYabg1FJaeMH7iUe2QRdi?node-id=24395-2) | Empty at inspection. No usable template was found on this page. |
| Agents playground | PAGE | [24288:24228](https://www.figma.com/design/nOYabg1FJaeMH7iUe2QRdi?node-id=24288-24228) | Existing work area; destination must follow the task, not this page name alone. |

## Mobile component library

File key: `8YfQ8OljtPhKsdbCxytn6Y`. Exact page spelling `Scafold` is preserved.

| Exact name | Node type | Direct reference | Use |
| --- | --- | --- | --- |
| Scaffold/Default | COMPONENT | [22495:10472](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=22495-10472) | Source key, properties, and remaining usage decisions: [scaffolds](scaffolds.md). |
| Bottom Sheet | COMPONENT_SET | [22495:10484](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=22495-10484) | Source variants and remaining mapping gap: [scaffolds](scaffolds.md). |
| AppButton | COMPONENT_SET | [22414:4648](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=22414-4648) | Observed key `216114b019072ecf8bd31dbb24ed3501478374a0`; inspect its required variants for the task. |
| IconButton | COMPONENT_SET | [22736:1011](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=22736-1011) | Observed key `a02ea814550aad35a8825c5eaeded376c82503fe`. |
| Chat • Template | PAGE | [22495:4527](https://www.figma.com/design/8YfQ8OljtPhKsdbCxytn6Y?node-id=22495-4527) | Page identity verified; contents not audited here. Do not claim a reusable template from the page name alone. |

## Mobile scenario references

File key: `jwDivkSTIiXrDEUtFfmsyE`. Page name includes a leading space:
` Phone / email (add, edit, remove)` —
[2:6](https://www.figma.com/design/jwDivkSTIiXrDEUtFfmsyE?node-id=2-6).

| Exact name | Node type | Direct reference |
| --- | --- | --- |
| Добавление номера телефона (Mobile) | FRAME | [271:24188](https://www.figma.com/design/jwDivkSTIiXrDEUtFfmsyE?node-id=271-24188) |
| Добавление почты | FRAME | [271:34690](https://www.figma.com/design/jwDivkSTIiXrDEUtFfmsyE?node-id=271-34690) |
| Изменение почты | FRAME | [297:40782](https://www.figma.com/design/jwDivkSTIiXrDEUtFfmsyE?node-id=297-40782) |
| Удаление почты | FRAME | [300:48611](https://www.figma.com/design/jwDivkSTIiXrDEUtFfmsyE?node-id=300-48611) |
| Изменение номера телефона (Mobile) | FRAME | [274:19501](https://www.figma.com/design/jwDivkSTIiXrDEUtFfmsyE?node-id=274-19501) |
| Удаление номера телефона (Mobile) | FRAME | [292:24177](https://www.figma.com/design/jwDivkSTIiXrDEUtFfmsyE?node-id=292-24177) |

These are existing scenario references, not a declaration of approved product
behavior or reusable screen templates. Names are duplicated elsewhere on the
page; use the IDs. Inspect individual screens and transitions for the task.

## Access and editing

Reading GitLab does not grant Figma access; reading Figma does not prove write
access. Use the connected Enqo account and inspect the specific file. Select the
output page from the user's task or an already authorized work area; if ambiguous,
resolve it before writing. Do not edit library source components during a scenario.

Follow the installed Figma tool's current API instructions. Return affected IDs,
inspect the result structurally and visually, and report any save/connection
failure as unconfirmed persistence. Never infer successful saving or publication
from a screenshot alone.
