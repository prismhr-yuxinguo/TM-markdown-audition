# Differences between `dash-gage2.component.html` (Mocks) and `dash-gage2.component.html` (Production)

## Table of Contents

-   [Relative Paths](#relative-paths)
-   [Differences](#differences)
-   [Prod Screenshots](#prod-screenshots)
-   [Mock Screenshots](#mock-screenshots)
-   [URL](#url)

### Relative Paths

-   **dash-gage2.component.html**: `components-ng-shared/projects/mocks-talent-ng/src/app/dashboard/dash-gage2/dash-gage2.component.html`
-   **dash-gage2.component.html**: `AgileHR/Talent/Talent.Web/ClientApp/src/app/dashboard/dash-gage2/dash-gage2.component.html`

### Differences

#### components-ng-shared/projects/mocks-talent-ng/src/app/dashboard/dash-gage2/dash-gage2.component.html

-   Contains a `<div>` with class `dashboard__card`.
-   Contains a `<dashboard-card-title>` component with a `[title]` attribute set to `'Summary'`.
-   Contains a `<style>` block defining styles for `.box-wrapper` and `.box`.
-   Contains a `<dashboard-card-body>` component with nested `<div>` elements displaying candidate statistics.
-   Contains an `<ejs-sparkline>` component with attributes `class`, `height`, `width`, `lineWidth`, `valueType`, `fill`, `type`, `negativePointColor`, `[border]`, `[dataSource]`, `[tooltipSettings]`, `xName`, and `yName`.

#### AgileHR/Talent/Talent.Web/ClientApp/src/app/dashboard/dash-gage2/dash-gage2.component.html

-   Contains a `<dashboard-card-title>` component with a `[title]` attribute set to `'Summary'`.
-   Contains a `<dashboard-card-body>` component with nested `<div>` elements displaying candidate statistics.
-   Contains an `<ejs-sparkline>` component with attributes `class`, `height`, `width`, `lineWidth`, `valueType`, `fill`, `type`, `negativePointColor`, `[border]`, `[dataSource]`, `[tooltipSettings]`, `xName`, and `yName`.

### This component is currently not implemented in production.

### Production Screenshots

N/A

### Mock Screenshots

N/A

### URL

N/A
