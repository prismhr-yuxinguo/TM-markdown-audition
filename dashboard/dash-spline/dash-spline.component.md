# Differences between `dash-spline.component.html` (Mocks) and `dash-spline.component.html` (Production)

## Table of Contents

-   [Relative Paths](#relative-paths)
-   [Differences](#differences)
-   [Prod Screenshots](#prod-screenshots)
-   [Mock Screenshots](#mock-screenshots)
-   [URL](#url)

### Relative Paths

-   **dash-spline.component.html**: `components-ng-shared/projects/mocks-talent-ng/src/app/dashboard/dash-spline/dash-spline.component.html`
-   **dash-spline.component.html**: `AgileHR/Talent/Talent.Web/ClientApp/src/app/dashboard/dash-spline/dash-spline.component.html`

### Differences

#### components-ng-shared/projects/mocks-talent-ng/src/app/dashboard/dash-spline/dash-spline.component.html

-   Contains a `<dashboard-card-title>` component with an `<input-dropdown>` element inside it.
-   Contains a `<dashboard-card-body>` component with a `<div>` element having class `preloader__wrapper` and a nested `<div>` element with class `preloader`.
-   Contains an `<ejs-chart>` component with attributes `[chartArea]`, `class`, `id`, `#splineChart`, `[enableCanvas]`, `[primaryXAxis]`, `[primaryYAxis]`, `[title]`, `[tooltip]`, `[annotations]`, `[legendSettings]`, and `[palettes]`.
-   Contains an `<e-series-collection>` component with a nested `<e-series>` element having attributes `[dataSource]`, `type`, `xName`, `yName`, `width`, and `[marker]`.

#### AgileHR/Talent/Talent.Web/ClientApp/src/app/dashboard/dash-spline/dash-spline.component.html

-   Contains a `<dashboard-card-title>` component with a `<select>` element inside it.
-   Contains a `<dashboard-card-body>` component with a `<div>` element having class `loader__wrapper` and a nested `<div>` element with class `loader`.
-   Contains an `<ejs-chart>` component with attributes `[chartArea]`, `class`, `id`, `#chartContainer`, `[enableCanvas]`, `[primaryXAxis]`, `[primaryYAxis]`, `[title]`, `[tooltip]`, `[annotations]`, `[legendSettings]`, and `[palettes]`.
-   Contains an `<e-series-collection>` component with a nested `<e-series>` element having attributes `[dataSource]`, `type`, `xName`, `yName`, `width`, and `[marker]`.

### Prod Screenshots

### dash-spline is implemented on dashboard.component.html, but not visible.

### Mock Screenshots

![Mock Screenshot](/assets/img/dash-ac-mock.png)

### URL

[link to the page in prod](https://piedpiper.agilehr.net)

[link to the page in mock environment](http://localhost:4340/dashboard)
