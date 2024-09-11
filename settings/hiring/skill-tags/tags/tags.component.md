# Differences between `tags.component.html` and `sps-tags.component.html`

## Table of Contents

-   [Relative Paths](#relative-paths)
-   [Differences](#differences)
-   [Prod Screenshots](#prod-screenshots)
-   [Mock Screenshots](#mock-screenshots)
-   [URL](#url)

### Relative Paths

-   **tags.component.html**: `AgileHR\Talent\Talent.Web\ClientApp\src\app\settings\hiring\skill-tags\tags\tags.component.html`
-   **sps-tags.component.html**: `components-ng-shared\projects\mocks-talent-ng\src\app\settings\tracking\track-pst\sps-tags\sps-tags.component.html`

### Differences

#### AgileHR\Talent\Talent.Web\ClientApp\src\app\settings\hiring\skill-tags\tags\tags.component.html

-   Contains a `<talent-grid>` component with various attributes such as `[allowNew]`, `[allowRowSelect]`, `(applyFilters)`, `[allowBulkActions]`, `[data]`, `exportFileName`, `[filters]`, `[filtersForm]`, `friendlyName`, `[initializing]`, `(rowSelected)`, `[searchFields]`, `(selected)`, `[selectActionTooltip]`, and `[selectOptions]`.
-   The `<talent-grid>` contains an `<ng-template>` with `#filtersTemplate` and a `[formGroup]` attribute bound to `filtersForm`.
-   The `<ng-template>` contains an `<input-dropdown>` component with attributes `[data]`, `[form]`, `formControlName`, `ngDefaultControl`, and `placeholder`.
-   The `<talent-grid>` contains an `<e-columns>` component with a single `<e-column>` component.
-   The `<e-column>` component has attributes `field` and `headerText`.
-   The `<e-column>` component contains an `<ng-template>` with `*hasKey`, `#template`, and `let-data`.
-   The `<ng-template>` contains an `<ejs-tooltip>` component with attributes `#tooltip` and `[content]`.
-   The `<ejs-tooltip>` contains an `<a>` element with class `grid-link disable-row-select` and a `(click)` event.
-   Contains a `<modal-base>` component with `[config]` and `[template]` attributes for `confirmationPopupConfig` and `deleteContent`, respectively.
-   Contains an `<ng-template>` with `#deleteContent` and a nested `<div>` element with the class `row`.
-   The `<div>` contains a nested `<div>` element with the class `col-xs-12` and a confirmation message.
-   Contains another `<modal-base>` component with `[config]` and `[template]` attributes for `editSetupModal` and `editSetupContent`, respectively.
-   Contains an `<ng-template>` with `#editSetupContent` and a nested `<fieldset>` element with a `[formGroup]` attribute bound to `tagFormGroup` and `[disabled]` bound to `!isEditable`.
-   The `<fieldset>` contains a `<settings-table>` component with multiple `<settings-row>` components.
-   The first `<settings-row>` component has attributes `[title]`, `[description]`, and `[required]`.
-   The first `<settings-row>` component contains an `<input-text>` component with attributes `[placeholder]`, `[required]`, `[form]`, `ngDefaultControl`, and `formControlName`.
-   The second `<settings-row>` component has attributes `[title]`, `[description]`, and `[required]`.
-   The second `<settings-row>` component contains an `<ejs-multiselect>` component with attributes `#muliselect`, `id`, `[value]`, `[dataSource]`, `[allowCustomValue]`, `(tagging)`, `(removing)`, `mode`, `placeholder`, and `[fields]`.

#### components-ng-shared\projects\mocks-talent-ng\src\app\settings\tracking\track-pst\sps-tags\sps-tags.component.html

-   Contains a `<grid-filters>` component with attributes `[centerTemplate]` and `[centerHeaderTemplate]`.
-   The `<grid-filters>` contains an `<ng-template>` with `#centerHeaderTemplate` and a nested `<div>` element with class `custom-toolbar`.
-   The `<div>` contains nested `<div>` elements with classes `custom-toolbar__wrapper`, `custom-toolbar__lc`, and `custom-toolbar__rc`.
-   The `<div>` contains an `<input-text>` component with attributes `[placeholder]` and `[cssClass]`.
-   The `<div>` contains a `<button-dropdown-grid>` component with attributes `[items]`, `tooltip`, and `[icon]`.
-   The `<div>` contains a `<button-base>` component with attributes `[title]`, `[tooltip]`, `(click)`, `onKeyPress`, `onKeyDown`, and `onKeyUp`.
-   The `<grid-filters>` contains an `<ng-template>` with `#centerContent` and a nested `<ejs-grid>` component with attributes `[enableAdaptiveUI]`, `[rowRenderingMode]`, `[allowPaging]`, and `[dataSource]`.
-   The `<ejs-grid>` contains an `<e-columns>` component with multiple `<e-column>` components.
-   The first `<e-column>` component has attributes `field` and `headerText`.
-   The second `<e-column>` component has attributes `field`, `textAlign`, `[template]`, and `width`.
-   Contains an `<ng-template>` with `#editbutton` and a nested `<button-dropdown-grid>` component with attributes `[items]`, `tooltip`, and `[callback]`.
-   Contains an `<ng-template>` with `#searchbar` and a nested `<input-text>` component with attributes `[placeholder]` and `[cssClass]`.
-   Contains a `<modal-base>` component with `[config]` and `[template]` attributes for `deleteModal` and `deleteContent`, respectively.
-   Contains an `<ng-template>` with `#deleteContent` and a nested `<div>` element with the class `row`.
-   The `<div>` contains a nested `<div>` element with the class `col-xs-12` and a confirmation message.
-   Contains another `<modal-base>` component with `[config]` and `[template]` attributes for `newTypeModal` and `newTypeContent`, respectively.
-   Contains an `<ng-template>` with `#newTypeContent` and a nested `<settings-table>` component with multiple `<settings-row>` components.
-   The first `<settings-row>` component has attributes `[title]` and `[required]`.
-   The first `<settings-row>` component contains an `<input-text>` component with attributes `[placeholder]` and `[required]`.
-   The second `<settings-row>` component has attributes `[title]`, `[required]`, and `[description]`.
-   The second `<settings-row>` component contains an `<input-text>` component with attributes `[placeholder]` and `[required]`.
-   Contains another `<modal-base>` component with `[config]` and `[template]` attributes for `editSetupModal` and `editSetupContent`, respectively.
-   Contains an `<ng-template>` with `#editSetupContent` and a nested `<settings-table>` component with multiple `<settings-row>` components.
-   The first `<settings-row>` component has attributes `[title]` and `[required]`.
-   The first `<settings-row>` component contains an `<input-text>` component with attributes `[placeholder]` and `[required]`.
-   The second `<settings-row>` component has attributes `[title]`, `[required]`, and `[description]`.
-   The second `<settings-row>` component contains an `<input-text>` component with attributes `[placeholder]` and `[required]`.

### Prod Screenshots

![Prod Screenshot](./tags-prod.png)

### Mock Screenshots

![Mock Screenshot](./sps-tags-mock.png)

### URL

[link to the page in prod](https://piedpiper.agilehr.net/core/settings/hiring/skill-tags)

[link to the page in mock environment](http://localhost:4340/settings/tracking/position-skill-tags)
