# Summary of `dismissal-reasons.component.html`

## Table of Contents

-   [Relative Path](#relative-path)
-   [Summary](#summary)
-   [Mock Screenshots](#mock-screenshots)
-   [Prod Screenshots](#prod-screenshots)
-   [URL](#url)

### Relative Path

-   **dismissal-reasons.component.html**: `AgileHR\Talent\Talent.Web\ClientApp\src\app\settings\hiring\lists\dismissal-reasons\dismissal-reasons.component.html`

### Summary

-   Contains a `<talent-grid>` component with various attributes and event bindings such as `[allowFiltering]`, `[allowBulkActions]`, `[allowRowSelect]`, `[allowNew]`, `[data]`, `[friendlyName]`, `exportFileName`, `[initializing]`, `(selected)`, `[selectActionTooltip]`, `[selectOptions]`, and `[searchFields]`.
-   The `<talent-grid>` contains an `<e-columns>` component with a single `<e-column>` component.
-   The `<e-column>` component has attributes `field` set to `"description"` and `headerText` set to `"Description"`.
-   The `<e-column>` component contains an `<ng-template>` with a `*hasKey` directive and a `#template` identifier.
-   The `<ng-template>` contains an `<ejs-tooltip>` component with a `[content]` attribute.
-   Inside the `<ejs-tooltip>`, there is an `<a>` element with a `class` attribute set to `'grid-link disable-row-select'` and a `(click)` event bound to the `onLinkClicked($event, data)` method.
-   Contains a `<modal-base>` component with `[config]` and `[template]` attributes for `createEditDismissalReasonsModal` and `newTypeContent`, respectively.
-   Contains an `<ng-template>` with `#newTypeContent` and a `[formGroup]` attribute bound to `createEditDismissalReasonForm`.
-   The `<ng-template>` contains a `<settings-table>` component with a nested `<settings-row>` component.
-   The `<settings-row>` component has attributes `[title]` set to `'Description'`, `[description]` set to an empty string, and `[required]` set to `true`.
-   Inside the `<settings-row>`, there is an `<input-text>` component with attributes `[form]` bound to `createEditDismissalReasonForm`, `formControlName` set to `"description"`, and `[placeholder]` set to `'Description'`.
-   Contains another `<modal-base>` component with `[config]` and `[template]` attributes for `deleteDismissalReasonsModal` and `deleteContent`, respectively.
-   Contains an `<ng-template>` with `#deleteContent`.
-   The `<ng-template>` contains a `<div>` element with the class `row`.
-   Inside the `<div>`, there is another `<div>` element with the class `col-xs-12` containing a confirmation message for deleting a dismissal reason record.

### This component is currently not implemented in mock environment.

### Mock Screenshots

N/A

### Prod Screenshots

![Prod Screenshot](./dismissal-reasons-prod.png)

### URL

[link to the page in prod](https://piedpiper.agilehr.net/core/settings/hiring/lists/dismissal-reasons)
