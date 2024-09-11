# Summary of `requisition-types.component.html`

## Table of Contents

-   [Relative Path](#relative-path)
-   [Summary](#summary)
-   [Mock Screenshots](#mock-screenshots)
-   [Prod Screenshots](#prod-screenshots)
-   [URL](#url)

### Relative Path

-   **requisition-types.component.html**: `AgileHR\Talent\Talent.Web\ClientApp\src\app\settings\hiring\lists\requisition-types\requisition-types.component.html`

### Summary

-   Contains a `<talent-grid>` component with various attributes and event bindings such as `[allowFiltering]`, `[allowBulkActions]`, `[allowRowSelect]`, `[allowNew]`, `[data]`, `[friendlyName]`, `exportFileName`, `[initializing]`, `(selected)`, `[selectActionTooltip]`, `[selectOptions]`, and `[searchFields]`.
-   The `[allowFiltering]`, `[allowBulkActions]`, and `[allowRowSelect]` attributes are set to `false`.
-   The `[allowNew]` attribute is bound to `allowNew`.
-   The `[data]` attribute is bound to `requisitionTypesList`.
-   The `[friendlyName]` attribute is set to `'Requisition Type'`.
-   The `exportFileName` attribute is set to `'Requisition Types'`.
-   The `[initializing]` attribute is bound to `initializing`.
-   The `(selected)` event is bound to the `selected($event)` method.
-   The `[selectActionTooltip]` attribute is bound to `selectActionTooltip`.
-   The `[selectOptions]` attribute is bound to `selectOptions`.
-   The `[searchFields]` attribute is set to `['description']`.
-   The `<talent-grid>` contains an `<e-columns>` component with a single `<e-column>` component.
-   The `<e-column>` component has attributes `field` set to `"description"` and `headerText` set to `"Description"`.
-   The `<e-column>` component contains an `<ng-template>` with a `*hasKey` directive and a `#template` identifier.
-   The `<ng-template>` contains an `<ejs-tooltip>` component with a `[content]` attribute.
-   Inside the `<ejs-tooltip>`, there is an `<a>` element with a `class` attribute set to `'grid-link disable-row-select'` and a `(click)` event bound to the `onLinkClicked($event, data)` method.
-   Contains a `<modal-base>` component with `[config]` and `[template]` attributes for `createEditRequisitionTypeModal` and `newTypeContent`, respectively.
-   Contains an `<ng-template>` with `#newTypeContent` and a `[formGroup]` attribute bound to `createEditRequisitionTypeForm`.
-   The `<ng-template>` contains a `<settings-table>` component with a nested `<settings-row>` component.
-   The `<settings-row>` component has attributes `[title]` set to `'Description'`, `[description]` set to an empty string, and `[required]` set to `true`.
-   Inside the `<settings-row>`, there is an `<input-text>` component with attributes `[form]` bound to `createEditRequisitionTypeForm`, `formControlName` set to `"description"`, and `[placeholder]` set to `'Description'`.
-   Contains another `<modal-base>` component with `[config]` and `[template]` attributes for `deleteRequisitionTypeModal` and `deleteContent`, respectively.
-   Contains an `<ng-template>` with `#deleteContent`.
-   The `<ng-template>` contains a `<div>` element with the class `row`.
-   Inside the `<div>`, there is another `<div>` element with the class `col-xs-12` containing a confirmation message for deleting a requisition type record.

### This component is currently not implemented in mock environment.

### Mock Screenshots

N/A

### Prod Screenshots

![Prod Screenshot](./requisition-types-prod.png)

### URL

[link to the page in prod](https://piedpiper.agilehr.net/core/settings/hiring/lists/requisition-types)
