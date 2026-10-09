# Figma references

Inspected 2026-10-09 with the Enqo Figma connection. These are exact observed
page/node names. The API returned `Document` for the document root; it did not
establish a human-readable file title. File keys and node links identify files
without inventing titles.

## Web

File key: `nOYabg1FJaeMH7iUe2QRdi`.

| Exact name | Node type | Direct reference | Use |
| --- | --- | --- | --- |
| App Shell | COMPONENT | [24227:2308](https://www.figma.com/design/nOYabg1FJaeMH7iUe2QRdi?node-id=24227-2308) | Source identity and slot: see [scaffolds](scaffolds.md). |
| Sheet | COMPONENT | [24227:16](https://www.figma.com/design/nOYabg1FJaeMH7iUe2QRdi?node-id=24227-16) | Has unpublished changes; see [scaffolds](scaffolds.md). |
| Templates | PAGE | [24395:2](https://www.figma.com/design/nOYabg1FJaeMH7iUe2QRdi?node-id=24395-2) | Empty at inspection. No usable template was found on this page. |
| Agents playground | PAGE | [24288:24228](https://www.figma.com/design/nOYabg1FJaeMH7iUe2QRdi?node-id=24288-24228) | Existing work area; destination must follow the task, not this page name alone. |

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
