# Summary of `billing-information.component.html`

## Table of Contents

-   [Relative Path](#relative-path)
-   [Summary](#summary)
-   [Mock Screenshots](#mock-screenshots)
-   [Prod Screenshots](#prod-screenshots)
-   [URL](#url)

### Relative Path

-   **billing-information.component.html**: `AgileHR\Talent\Talent.Web\ClientApp\src\app\settings\hiring\billing-information\billing-information.component.html`

### Summary

-   Contains a `<page-title>` component with a `[title]` attribute set to `'Billing Information'`.
-   Contains a `<talent-footer>` component with attributes `(customButtonClicked)`, `[customButtons]`, `[nextVisible]`, `[prevVisible]`, `(saveClicked)`, `[saveEnabled]`, and `[saveVisible]`.
-   Contains an `<ejs-tab>` component with `id="element"`.
-   The `<ejs-tab>` contains an `<e-tabitems>` component with two `<e-tabitem>` components.
-   The first `<e-tabitem>` has two `<ng-template>` elements: one with `#headerText` containing a `<div>` with the text `User Billing Information`, and another with `#content` containing a `<ng-container>` with a `[formGroup]` attribute bound to `billInfoForm`.
-   Inside the `<ng-container>`, there is a `<settings-table>` component with multiple `<settings-row>` components.
-   The `<settings-row>` components have attributes such as `[title]`, `[description]`, `[required]`, and `*ngIf`.
-   The `<settings-row>` components contain various input components such as `<input-text>`, `<ejs-maskedtextbox>`, and `<input-dropdown>`.
-   The input components have attributes such as `[placeholder]`, `[form]`, `formControlName`, `[enabled]`, `mask`, `floatLabelType`, and `[required]`.
-   Some `<settings-row>` components contain `<p>` elements with `*ngIf` directives for displaying error messages.
-   The second `<e-tabitem>` has two `<ng-template>` elements: one with `#headerText` containing a `<div>` with the text `Transaction History`, and another with `#content` containing a `<talent-grid>` component.
-   The `<talent-grid>` component has attributes such as `[allowBulkActions]`, `[allowFiltering]`, `[allowNew]`, `[allowRowSelect]`, `[data]`, `exportFileName`, `friendlyName`, `[searchFields]`, `[selectActionTooltip]`, `[selectOptions]`, `(selected)`, and `(sortDir)`.
-   The `<talent-grid>` contains an `<e-columns>` component with multiple `<e-column>` components.
-   The `<e-column>` components have attributes such as `field`, `headerText`, `maxWidth`, `[sortComparer]`, and `format`.
-   Contains a `<modal-base>` component with `[config]` and `[template]` attributes bound to `confirmationPopupConfig` and `confirmationContent`, respectively.
-   Contains an `<ng-template>` with `#confirmationContent` and nested `<div>` elements for displaying a confirmation message.

### This component is currently not implemented in production or mock environment.

### Mock Screenshots

N/A

### Prod Screenshots

N/A

### URL

N/A
