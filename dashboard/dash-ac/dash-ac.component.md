# Differences between `dash-ac.component.html` (Mocks) and `dash-ac.component.html` (Production)

## Table of Contents

-   [Relative Paths](#relative-paths)
-   [Differences](#differences)
-   [Prod Screenshots](#prod-screenshots)
-   [Mock Screenshots](#mock-screenshots)
-   [URL](#url)

### Relative Paths

-   **dash-ac.component.html**: `components-ng-shared/projects/mocks-talent-ng/src/app/dashboard/dash-ac/dash-ac.component.html `
-   **dash-ac.component.html**: `AgileHR/Talent/Talent.Web/ClientApp/src/app/dashboard/dash-ac/dash-ac.component.html `

### Differences

#### components-ng-shared/projects/mocks-talent-ng/src/app/dashboard/dash-ac/dash-ac.component.html

-   Contains a `<div>` with class `dashboard__card`.
-   Contains a `<dashboard-card-title>` component with a `[title]` attribute set to `'Active Candidates'`.
-   Contains an `<input-dropdown>` component with attributes `[data]`, `[value]`, `[placeholder]`, and `[floatLabelType]`.
-   Contains a `<dashboard-card-body>` component.
-   Contains an `<ejs-grid>` component with attributes `[enableAdaptiveUI]`, `[rowRenderingMode]`, `[allowPaging]`, `[dataSource]`, `allowSorting`, `allowPaging`, `[loadingIndicator]`, and `height`.
-   Contains an `<e-columns>` component with multiple `<e-column>` components.
-   Contains an `<ng-template>` with `#editbutton`.
-   Contains an `<ng-template>` with `#evealuateStatus`.

#### AgileHR/Talent/Talent.Web/ClientApp/src/app/dashboard/dash-ac/dash-ac.component.html

-   Contains a `<dashboard-card-title>` component with a `[title]` attribute set to `'Active Candidates'`.
-   Contains an `<input-dropdown>` component with attributes `[form]`, `formControlName`, `[data]`, `[placeholder]`, `[floatLabelType]`, and `(optionSelected)`.
-   Contains a `<dashboard-card-body>` component.
-   Contains a `<div>` with `id="custom-grid"`.
-   Contains a `<talent-grid>` component with attributes `[allowSorting]`, `[allowPaging]`, `[allowNew]`, `[allowFiltering]`, `[allowBulkActions]`, `[allowSearch]`, `[allowExport]`, `[gridHeight]`, `[data]`, `(initialized)`, `(selected)`, `(dataStateChange)`, `[selectOptions]`, `[loading]`, and `[isServerSide]`.
-   Contains an `<e-columns>` component with multiple `<e-column>` components.
-   Contains an `<ng-template>` with `#template`.
-   Contains an `<ejs-tooltip>` component with attributes `*hasKey`, `#tooltip`, and `[content]`.
-   Contains an `<a>` tag with class `grid-link disable-row-select` and `(click)` event.

### Prod Screenshots

![Prod Screenshot](/assets/img/dash-ac-prod.png)

### Mock Screenshots

![Mock Screenshot](/assets/img/dash-ac-mock.png)

### URL

[link to the page in prod](https://piedpiper.agilehr.net)
