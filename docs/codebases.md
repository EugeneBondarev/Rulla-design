# Code references

Checked against remote `develop` heads on 2026-10-09. Links are pinned to the
inspected revisions. Refresh the relevant source before a task; these commits
are not claims about a deployed release. Do not reset an existing working tree
to these revisions.

| Repository | Inspected branch and commit | Purpose |
| --- | --- | --- |
| [Rulla-design](https://github.com/EugeneBondarev/Rulla-design) | Initially empty; `main` reported by GitHub on 2026-10-09. | Current home of these agent instructions and copied typography JSON. |
| [Enqo.Design](https://git.aimadev.space/platform/Enqo.Design) | `develop`, `63c349132255892fcb857652774053fc204de452`; earlier instruction draft at `a6c4b5fcdd572420322a1e03deb17b7a9c75f798`. | Provenance of typography and the earlier draft; not the current instruction entry point. |
| [Enqo.Platform.WebClient](https://git.aimadev.space/platform/Enqo.Platform.WebClient) | `develop`, `7b6d94c500f3108e55bdb7f84e267d7a8cd3b26e` | Web implementation. |
| [Enqo.Mobile](https://git.aimadev.space/platform/Enqo.Mobile) | `develop`, `d12f3e6819ce70f892bbb2c7df4ee16955b694c6` | Flutter implementation. |

The user moved the instruction workspace to Rulla-design on 2026-10-09. This
does not establish new locations for the Web or Mobile code; their verified
GitLab references remain above. Release-to-production revisions and code
maintainers have not been established here.

## Web

| Exact source path | What to inspect |
| --- | --- |
| [src/platform/App.vue](https://git.aimadev.space/platform/Enqo.Platform.WebClient/-/blob/7b6d94c500f3108e55bdb7f84e267d7a8cd3b26e/src/platform/App.vue) | Application composition and route-meta-dependent shell. |
| [src/platform/router.js](https://git.aimadev.space/platform/Enqo.Platform.WebClient/-/blob/7b6d94c500f3108e55bdb7f84e267d7a8cd3b26e/src/platform/router.js) | Route definitions and meta used to select layouts. |
| [src/layouts/Project.vue](https://git.aimadev.space/platform/Enqo.Platform.WebClient/-/blob/7b6d94c500f3108e55bdb7f84e267d7a8cd3b26e/src/layouts/Project.vue) | Project layout. |
| [src/layouts/Default.vue](https://git.aimadev.space/platform/Enqo.Platform.WebClient/-/blob/7b6d94c500f3108e55bdb7f84e267d7a8cd3b26e/src/layouts/Default.vue) | Default layout. |
| [src/layouts/Empty.vue](https://git.aimadev.space/platform/Enqo.Platform.WebClient/-/blob/7b6d94c500f3108e55bdb7f84e267d7a8cd3b26e/src/layouts/Empty.vue) | Empty layout. |
| [src/components/default/EqSelect.vue](https://git.aimadev.space/platform/Enqo.Platform.WebClient/-/blob/7b6d94c500f3108e55bdb7f84e267d7a8cd3b26e/src/components/default/EqSelect.vue) | Select implementation and API; not an alias for the text field. |
| [src/components/default/EqTextField.vue](https://git.aimadev.space/platform/Enqo.Platform.WebClient/-/blob/7b6d94c500f3108e55bdb7f84e267d7a8cd3b26e/src/components/default/EqTextField.vue) | Text-field implementation and API. |
| [src/styles/global.scss](https://git.aimadev.space/platform/Enqo.Platform.WebClient/-/blob/7b6d94c500f3108e55bdb7f84e267d7a8cd3b26e/src/styles/global.scss) | Global styles and CSS custom properties. |
| [src/plugins/vuetify.js](https://git.aimadev.space/platform/Enqo.Platform.WebClient/-/blob/7b6d94c500f3108e55bdb7f84e267d7a8cd3b26e/src/plugins/vuetify.js) | Vuetify configuration and theme values. |
| [src/styles/typography.css](https://git.aimadev.space/platform/Enqo.Platform.WebClient/-/blob/7b6d94c500f3108e55bdb7f84e267d7a8cd3b26e/src/styles/typography.css) | Typography CSS. |

`App.vue` reads `$route.meta.isRoot` and `$route.meta.layout`. A root route renders
its layout and `router-view`; the other branch uses `v-app`, `MainMenu`, `TopBar`,
`v-main`, `AiSidebar`, and the selected layout/view. Therefore an agent must
inspect the requested route, not apply one shell composition to every screen.
This architecture does not prove a mapping to every similarly named Figma node.

## Mobile

| Exact source path | What to inspect |
| --- | --- |
| [common/lib/core/services/router/router.dart](https://git.aimadev.space/platform/Enqo.Mobile/-/blob/d12f3e6819ce70f892bbb2c7df4ee16955b694c6/common/lib/core/services/router/router.dart) | Actual route and screen selection. |
| [common/lib/core/services/router/adaptive_home_shell/adaptive_home_shell.dart](https://git.aimadev.space/platform/Enqo.Mobile/-/blob/d12f3e6819ce70f892bbb2c7df4ee16955b694c6/common/lib/core/services/router/adaptive_home_shell/adaptive_home_shell.dart) | AdaptiveHomeShell: home master/detail navigation. |
| [common/lib/core/services/router/sheet_shell/sheet_shell_route_data.dart](https://git.aimadev.space/platform/Enqo.Mobile/-/blob/d12f3e6819ce70f892bbb2c7df4ee16955b694c6/common/lib/core/services/router/sheet_shell/sheet_shell_route_data.dart) | SheetShellRouteData: phone/tablet presentation choice. |
| [common/lib/core/services/router/pages/modal_bottom_sheet_page.dart](https://git.aimadev.space/platform/Enqo.Mobile/-/blob/d12f3e6819ce70f892bbb2c7df4ee16955b694c6/common/lib/core/services/router/pages/modal_bottom_sheet_page.dart) | ModalBottomSheetPage, showScaffoldedModalBottomSheet, ScaffoldedModalBottomSheetRoute. |
| [common/lib/shared/presentation/widgets/text_field/text_field.dart](https://git.aimadev.space/platform/Enqo.Mobile/-/blob/d12f3e6819ce70f892bbb2c7df4ee16955b694c6/common/lib/shared/presentation/widgets/text_field/text_field.dart) | AppTextField implementation. |
| [common/lib/shared/presentation/theme/colors/tokens.dart](https://git.aimadev.space/platform/Enqo.Mobile/-/blob/d12f3e6819ce70f892bbb2c7df4ee16955b694c6/common/lib/shared/presentation/theme/colors/tokens.dart) | Color token definitions. |
| [common/lib/shared/presentation/theme/colors/app_color_theme.dart](https://git.aimadev.space/platform/Enqo.Mobile/-/blob/d12f3e6819ce70f892bbb2c7df4ee16955b694c6/common/lib/shared/presentation/theme/colors/app_color_theme.dart) | AppColorTheme and semantic color API. |
| [common/lib/shared/presentation/theme/typography/app_text_theme.dart](https://git.aimadev.space/platform/Enqo.Mobile/-/blob/d12f3e6819ce70f892bbb2c7df4ee16955b694c6/common/lib/shared/presentation/theme/typography/app_text_theme.dart) | AppTextTheme definitions. |

`AdaptiveHomeShell` returns the detail navigator on phones and builds a resizable
master/detail layout on tablets. It is not a generic screen scaffold.
`SheetShellRouteData.pageBuilder` uses `MaterialPage` on tablets and
`ModalBottomSheetPage.draggable` on phones. The specific route must establish
whether this shell applies. Presentation classes do not identify a Figma
component, and a bottom-sheet content component does not define navigation.

## Access

Open Rulla-design as the task workspace. Read sibling code repositories only after
checking their remotes, revision, local changes, and applicable instructions.
Use an existing authorized Git connection or checkout; do not request tokens in
chat. A GitLab browser session or an installed GitLab plugin alone does not prove
CLI/API read or push access to this self-managed host. Report each capability
only after the corresponding operation succeeds.

Rules in this repo are not automatically inherited by agents launched in another
repository. Explicitly load this AGENTS.md and its needed skills there, or start
here and grant access to the relevant code checkout. Do not silently modify the
other repository's instructions.
