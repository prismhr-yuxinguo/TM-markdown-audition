# Differences between `dash-cws.component.html` (Mocks) and `dash-cws.component.html` (Production)

## Table of Contents

-   [Relative Paths](#relative-paths)
-   [Differences](#differences)
-   [Prod Screenshots](#prod-screenshots)
-   [Mock Screenshots](#mock-screenshots)
-   [URL](#url)

### Relative Paths

-   **dash-cws.component.html (Mocks)**: `components-ng-shared/projects/mocks-talent-ng/src/app/dashboard/dash-cws/dash-cws.component.html`
-   **dash-cws.component.html (Production)**: `AgileHR/Talent/Talent.Web/ClientApp/src/app/dashboard/dash-cws/dash-cws.component.html`

### Differences

#### components-ng-shared/projects/mocks-talent-ng/src/app/dashboard/dash-cws/dash-cws.component.html

-   Contains a `<div>` with class `preloader__wrapper` and `*ngIf="!showChart"`.
-   Contains an `<ejs-accumulationchart>` component with attributes `[legendSettings]`, `[tooltip]`, `[title]`, `[enableSmartLabels]`, `[enableAnimation]`, `[enableBorderOnMouseMove]`, and `*ngIf="showChart"`.
-   The `<e-accumulation-series>` component has attributes `[dataSource]`, `xName`, `yName`, `innerRadius`, `[dataLabel]`, `[radius]`, `tooltipMappingName`, and `[palettes]`.

#### AgileHR/Talent/Talent.Web/ClientApp/src/app/dashboard/dash-cws/dash-cws.component.html

-   Contains an `<input-dropdown>` component with attributes `[ngClass]`, `[form]`, `formControlName`, `[data]`, `[placeholder]`, `[floatLabelType]`, and `(optionSelected)`.
-   Contains a `<div>` with class `preloader__wrapper` and `*ngIf="showChart"`.
-   Contains a `<div>` with `*ngIf="!showChart && !chartData?.length"` displaying "No data available to display."
-   Contains an `<ejs-accumulationchart>` component with attributes `[legendSettings]`, `[tooltip]`, `[title]`, `[enableSmartLabels]`, `[enableAnimation]`, `[enableBorderOnMouseMove]`, `*ngIf="!showChart && chartData?.length"`, and `(pointClick)`.
-   The `<e-accumulation-series>` component has attributes `[dataSource]`, `xName`, `yName`, `innerRadius`, `[dataLabel]`, `[radius]`, `tooltipMappingName`, and `[palettes]`.

### Production Screenshots

![Prod Screenshot](/assets/img/dash-ac-prod.png)

### Mock Screenshots

![Mock Screenshot](/assets/img/dash-ac.mock.png)

### URL

[link to the page in prod](https://piedpiper.agilehr.net)

[link to the page in mock environment](http://localhost:4340/dashboard)
